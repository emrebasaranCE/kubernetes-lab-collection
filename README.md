In this example we have 3 different backend apps and in the end we will have 3 different container which needs to communicate with each other. This example does not care about data persistency. Therefor the data will be vanished after using `docker-compose down` or after the deployment delete.

`auth_api` used for authenticating users  
`tasks_api` store and return new tasks  
`users_api` creating and login users in

1) First we created a users-deployment.yaml to create a deployment.
 
2) We created a users-service.deployment.yaml for our pod to communicate with outside our cluster. To our pod to communicate with the outside world, we select the service type as a LoadBalancer, this way while its balancing the incoming traffic it also conntects to outer world.

3) Then we configured users-deployment file for auth container since we want these two container in the same pod.

4) Then our instructor decided we should seperate this containers and therefor we are creating seperate auth-deployment.yaml file.

5) After creating other .yaml files for each app which looks like this:
    - auth-deployment.yaml
    - auth-service.yaml
    - users-deployment.yaml
    - users-service.yaml
    - tasks-deployment.yaml
    - tasks-service.yaml

6) Now we all of our containers are in different deployments which means they are in seperate pods. Now all we have to do is the communications of this pods.