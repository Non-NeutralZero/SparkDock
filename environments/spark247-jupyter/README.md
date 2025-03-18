# Spark 247 & Jupyter

## Components
This environment is preconfigured with the following tools and versions:

| **Package**       | **Version**   |
|--------------------|---------------|
| Python            | 3.x           |
| Java (OpenJDK)    | 8             |
| Apache Spark      | 2.4.7         |
| Anaconda          | 2019.10       |


## Docker Commands

### Build the Docker Image
To create the Docker image with all dependencies:
```bash
docker build --tag spark247-jupyter .
```

### Run the Container
Start the container and expose Jupyter Notebook on port `8889`:
```bash
docker run -t -d -p 8889:8889 spark247-jupyter:latest
```

### Access Jupyter Notebook
Once the container is running, open your browser and navigate to:
```
http://localhost:8889
```
*(Check the terminal logs for the authentication token.)*

---

