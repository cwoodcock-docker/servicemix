# Servicemix
Basic Dockerfile for Apache Servicemix.

This intended primarily intended for development environments rather than production.

## Versions
* Java: 7u79-jdk (OpenJDK)
* Servicemix: 6.0.0

## Usage
```
docker run -d \
  --name servicemix \
  -p 1099:1099 \
  -p 5005:5005 \
  -p 8101:8101 \
  -p 44444:44444 \
  -p 61616:61616 \
  -p 8181:8181 \
  -v ~/smix/deploy:/deploy \
  -v ~/smix/data:/data \
  cwoodcock/servicemix
```

In production you'll probably want data containers rather than mapping to the local filesystem.  

### Doco TODO
* data containers
* karaf shell
* nsenter

## Volumes
* `/opt/servicemix/deploy` - SMIX JARs and deployment descriptors
* `/opt/servicemix/data` - SMIX data

## Exposed Ports
* 1099 - RMI
* 5005 - Remote debugging
* 8101 - Karaf SSH
* 44444 - JMX
* 61616 - ActiveMQ

## License

	Copyright (C) 2015 Colin Woodcock

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <http://www.gnu.org/licenses/>.