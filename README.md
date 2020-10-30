# Description

Docker implementation of hiawatha webserver (https://www.hiawatha-webserver.org/).

The container will run as www-data, so ports <1024 are not usable.

# Usage
By default, the container will listen to 8080 without any SSL configuration. The website root directory is located at /var/www/hiawatha
```
docker run -p 8080:8080 ybovard/hiawatha:10.11-bullseye
```

To change the default behaviour, either replace the original configuration file (/etc/hiawatha/hiawatha.conf) or :
```
docker run -p 8080:8080 ybovard/hiawatha:10.11-bullseye -c <new_hiawatha_config_path>
```

# Build instructions
to build a docker container, do the following:
```
docker build -t hiawatha:10.11-bullseye --build-arg HIAWATHA_VERSION=10.11 -f Dockerfile.bullseye .
```

