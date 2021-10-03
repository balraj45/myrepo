csvserver
PART 1 Solution

docker run -d infracloudio/csvserver:latest
o/p : 2021/10/02 06:50:51 error while reading the file "/csvserver/inputdata": open /csvserver/inputdata: no such file or directory

created a gencsv.sh file to generate input data file

ran gencsv.sh and inputfile is generated

docker run -d -v $PWD/inputFile:/csvserver/inputdata infracloudio/csvserver:latest

b74cccc60233bdf346001b53f595cf53ca9d7069c04ec04cab7135194090cd1b

docker exec -it b74cccc60233bdf346001b53f595cf53ca9d7069c04ec04cab7135194090cd1b bash
the port is running at 9300 to run the container in 9393 port use the following command for port mapping

docker run -p 9393:9300 -v $PWD/inputFile:/csvserver/inputdata infracloudio/csvserver:latest

docker run -p 9393:9300 -v $PWD/inputFile:/csvserver/inputdata -e CSVSERVER_BORDER=Orange infracloudio/csvserver:latest Set the environment variable CSVSERVER_BORDER to have value Orange.

PART 2

cd solution

Run the docker compose command docker-compose up

To start the service in background use docker-compose up -d

PART 3

Created a prmetheus.yaml config file by adding csvserver target and mounted the prometheus.yaml inside the container in compose file.
