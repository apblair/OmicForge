# Use the official Jupyter Data Science Notebook as the base image
FROM jupyter/datascience-notebook:latest

# Switch to root user to install system-level dependencies
USER root

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    nodejs \
    npm \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

# Switch back to jovyan user
USER jovyan

# Install required Python packages
RUN pip install --no-cache-dir \
    dash \
    dash-bio==1.0.1 \
    plotly \
    jupyter-dash  # Install Dash JupyterLab Extension via pip

# Enable the Dash extension in JupyterLab
RUN jupyter lab build

# Set the working directory
WORKDIR /home/jovyan

# Expose the default JupyterLab port
EXPOSE 8889
EXPOSE 8060

# Command to start JupyterLab
CMD ["start-notebook.sh", "--NotebookApp.token=''"]
