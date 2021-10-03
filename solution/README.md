this below commands is used to execute the part -1
 
 chmod 777 inputFile
 chmod 777 gencsv.sh
 docker run -d  -v /home/ubuntu/csvserver/solution/inputFile:/csvserver/inputdata -p 9393:9300 infracloudio/csvserver:latest
