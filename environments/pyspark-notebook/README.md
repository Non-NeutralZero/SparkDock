# PySpark & Jupyter Environment

A Docker-based environment for running PySpark and Jupyter Notebooks with Kerberos support (optional). 
Works for interactive ETL pipelining, and interactive machine learning workflows developement.


### Prerequisites
- Docker Engine
- Docker Compose v1.29.2+
- make (optional)

```shell
# Clone this repository
git clone https://github.com/your-username/spark-environments
cd spark-environments/environments/pyspark-jupyter

# Start the environment (Docker Compose)
./start_pysparkjupyter.sh
```

### Setup
- Option 1, Execute the script globally

Add start_pysparkjupyter.sh to your ~/scripts (or your $PATH added scripts directory) so you don't have to cd to the project's directory to start the environment (see: https://askubuntu.com/questions/153251/launch-shell-scripts-from-anywhere)

```shell
mkdir -p ~/scripts 
cp start_pysparkjupyter.sh ~/scripts/
echo 'export PATH="$HOME/scripts:$PATH"' >> ~/.bashrc  
source ~/.bashrc
```

- Option 2, cd to the project's directory and run the script
```shell
cd /path/to/pyspark-jupyter
docker-compose -f pysparkjupyterenv.yml down && \
docker-compose -f pysparkjupyterenv.yml build && \
docker-compose -f pysparkjupyterenv.yml up -d
``` 

### Kerberos Configuration (Optional)
For Kerberized Hadoop clusters:
- Edit krb5.conf with your cluster settings
- Mount your keytab file in the Docker Compose YML:
```yaml
volumes:
  - ./krb5.conf:/etc/krb5.conf
  - /path/to/your/keytab:/etc/security/keytabs/user.keytab
```
