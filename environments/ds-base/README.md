# Data Science Comprehensive Environment

This repository contains a Dockerfile that creates a comprehensive environment for data science and machine learning projects based on Debian 11 with Anaconda Python 3.9 and Mamba package manager.

## Features

- **Debian 11** base operating system
- **Anaconda Python 3.9** distribution
- **Mamba** package manager for faster dependency resolution
- Common system libraries for data visualization and GUI applications

## Building the Image

To build the Docker image, navigate to the directory containing the Dockerfile and run:

```bash
docker build -t data-science-env .
```

