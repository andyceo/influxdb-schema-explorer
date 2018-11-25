InfluxDB Schema Explorer
========================

This project is aimed to explore InfluxDB schema and data.


## Installation and usage

### Usage on raw system

You should have Python 3 and `pip` utility installed on your system.

To be able to execute `influxdb-schema-explorer.py` script on your system, just install needed packages with pip:

    pip install -r requirements.txt

Also this project is depend on [andyceo/pylibs](https://github.com/andyceo/pylibs) mixed libraries. The work to separate project from this dependency is on the way.

And after that you can check your InlfuxDB:

    /path/to/influxdb-schema-explorer.py --influxdb-host example.com --inlfuxdb-port 8086 --influxdb-user root --influxdb-password="secretsecret" --influxdb-database your-db

Use `--help` option to see available options.


### Usage with Docker

#### Build Docker image

    sudo docker build -t influxdb-schema-explorer:latest .

You can use this image from Docker Hub: [andyceo/influxdb-schema-explorer](https://hub.docker.com/r/andyceo/influxdb-schema-explorer)


#### Explore your InfluxDB with Docker

Get help message:

    sudo docker run --rm andyceo/influxdb-schema-explorer --help

Explore your InfluxDB:

    sudo docker run --rm andyceo/influxdb-schema-explorer --influxdb-host example.com --inlfuxdb-port 8086 --influxdb-user root --influxdb-password="secretsecret" --influxdb-database your-db
