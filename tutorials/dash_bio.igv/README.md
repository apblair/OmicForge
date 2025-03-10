# Dash Bio IGV Viewer in JupyterLab
📌 Reference: [dash_bio.igv](https://dash.plotly.com/dash-bio/igv)

This tutorial provides a containerized environment to run a Dash Bio IGV Viewer alongside JupyterLab, allowing interactive genomic visualization within a Jupyter notebook or as a standalone Dash application.

## 🚀 Installation & Setup

To build with fresh dependencies, add the --build flag:

```bash
docker compose up --build -d
```

## ⚙️ Configuration

The docker-compose.yaml file maps the necessary ports:


```yaml
ports:
      - "8889:8888"  # JupyterLab
      - "8060:8060"  # Dash App
```

The Dockerfile ensures the appropriate ports are exposed:


```Dockerfile
# Expose the default JupyterLab port
EXPOSE 8889
EXPOSE 8060
```

## 📂 Customization
* Modify the ports section in docker-compose.yaml if you need different port mappings.
* Add additional Python dependencies by updating the Dockerfile.
* Adjust the IGV genome browser settings inside your Dash app (genome="hg38", custom tracks, etc.).