In this example we have 3 different backend apps and in the end we will have 3 different container which needs to communicate with each other. This example does not care about data persistency. Therefor the data will be vanished after using `docker-compose down` or after the deployment delete.

`auth_api` used for authenticating users  
`tasks_api` store and return new tasks  
`users_api` creating and login users in

1) First we created a users-deployment.yaml to create a deployment.

2) We created a users-service.deployment.yaml for our pod to communicate with outside our cluster.

3) Then we configured users-deployment file for auth container since we want these two container in the same pod.

4) Then our instructor decided we should seperate this containers and therefor we are creating seperate auth-deployment.yaml file.

5) Manage pod-to-pod communication.