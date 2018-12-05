InfluxDB Schema Explorer
========================

This project is aimed to explore InfluxDB schema and data.


## Installation and usage with git and pip on Ubuntu

You should have Python 3 and `pip` utility installed on your system.

Clone the project:

    git clone git@github.com:andyceo/influxdb-schema-explorer.git

Install needed packages with pip:

    pip install -r requirements.txt

Also this project is depend on [andyceo/pylibs](https://github.com/andyceo/pylibs) mixed libraries. The work to separate project from this dependency is on the way. For now, you should clone [andyceo/pylibs](https://github.com/andyceo/pylibs) inside this project's directory:

    cd influxdb-schema-explorer
    git clone git@github.com:andyceo/pylibs.git

Everything now is ready. You can now explore your InlfuxDB schema:

    ./influxdb-schema-explorer.py --influxdb-host example.com --inlfuxdb-port 8086 --influxdb-user root --influxdb-password="secretsecret" --influxdb-database your-db

Use `--help` option to see available options:

    ./influxdb-schema-explorer.py --help


## Build your own Docker image

You can build your own Docker image to package this project in single image. See project's [Dockerfile](Dockerfile) for reference.

    sudo docker build -t influxdb-schema-explorer:latest .

You can use this official autobuilded image from Docker Hub: [andyceo/influxdb-schema-explorer](https://hub.docker.com/r/andyceo/influxdb-schema-explorer)


## Explore your InfluxDB schema with Docker version of this utility

Get help message:

    sudo docker run --rm andyceo/influxdb-schema-explorer --help

Explore your InfluxDB:

    sudo docker run --rm andyceo/influxdb-schema-explorer --influxdb-host example.com --inlfuxdb-port 8086 --influxdb-user root --influxdb-password="secretsecret" --influxdb-database your-db

If your InfluxDB is running as Docker Swarm service and use overlay network that accept regular containers to attach to it, you can add `--net` parameter:

    sudo docker run --rm --net your_influxdb_overlay_network andyceo/influxdb-schema-explorer --influxdb-host example.com --inlfuxdb-port 8086 --influxdb-user root --influxdb-password="secretsecret" --influxdb-database your-db

After successfull execution, you will get something like this:

![Usage example](docs/usage_example.png?raw=true "Usage example")
