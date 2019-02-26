# devops-test
to deploy nodejs app using helm i did the following:

    1- Create an image for every microservice 
    2- create helm  files
    3- create deployment for these apps



we shoud edit in file .env in app acceleration-calc as follow:

DV_URL=http://acceleration-dv:3001/dv
A_URL=http://acceleration-a:3002/a
   
Using the code that can be found here https://github.com/join-com/devops-challenge
   

create helm file for every app:

	helm create acceleration-a
	helm create acceleration-dv
	helm create acceleration-calc


every deployment has Dockerfile. 
Run this command for every app as follow:
    
    docker build -t acceleration-a .
    docker build -t acceleration-dv .
    docker build -t acceleration-calc .

   
now we will deploy kubernetes deployment for our apps :
inside every deployment dir run this command:
     
    helm install --name acceleration-a .
    helm install --name acceleration-pv .
    helm install --name acceleration-calc .