1.Base image 
    node:20-slim - Node.js supports the development of my MERN stack application.The specified image is stable will keep the image size small.

2.Dockerfle directives
    FROM  node:20-slim    - used as my base image
    WORKDIR /app - /app   - specifies my app's directory
    COPY package*.json ./ - copy the package.json to my app's directory
    RUN npm install       - to intsall the dependencies 
    COPY . .              - to copy all the contents into the image
    EXPOSE 5000 & 3000    - expose image to specified port
    CMD ["npm","start"]   - command used to start the application 
    #Introduced multistages to reduce the image size.

3.Docker-compose Networking
    Introduced a custom network "mern-network" that is used by all services.
    The network uses bridge driver.
    The services have specific ports mapped

4.Docker-compose Volume
    Used volumes to back up data in the database(mymongodb).
    Specified directory path : /home/mariam/Devopstrain/mongo-backup:/data/db

5.Git workflow
        Introduced new files,modified new and existing files then made commits to local repositories and later pushed to remote repositories.

6.The application runs successfully based on a well documented docker compose and restart tag keeps it up and running.One is able to view the application on the specified port.

7.Docker tags and names.
    On the docker compose file,the images have semver versions and container names for ease of identification.
    image: "mariamsenzia/backend:v1.0.0"     container_name: node-api
    image: "mariamsenzia/client:v1.0.0"      container_name: react-ui
    image: "mongo"                           container_name: mongo-db




       ANSIBLE AUTOMATION
1.Configure ansible environment.
   Set up the environment by provisioning a vagrant virtual machine with the latest ubuntu server.
   create hosts file which acts as the inventory and holds ip addresses.
   Create ansible.cfg to customize yor project.

2.Create playbook.yml
    Use plays to install and set up docker and other dependencies.
    Use plays to start services.
    Use plays to copy docker compose to the virtual machine and deploy the Yolo app.
    Introduce roles to implement docker set up task using ansible galaxy.
    Introduce variables.
    Introduce tags to specify certain tasks when running.

3.Execute playbook.yml  

4.Confirm if the service deployed are running.





        KUBERNETES DEPLOYMENT
1.Choice of kubernetes Objects used for deployment.
    Created deployment.yml files that contain the following obejects:
       1. apiVersion  - states the verion of k8s Api used to create the project.
       2. kind        - states the kind of object you want to create e.g Deployment & Service.
       3. metadata    - identifies the project using the name string.
       4. spec        - has the desired specifications.
                      - contains objects like replicas,template,selectors and spec which contains specifications of the containers.

    In the mongo-deployment.yml,the spec object included volumes and volumeMounts since the use of persistent volumes was used. Secret object was also used to store the passowrd.


2.Method used to expose pods to internet traffic.
    Ingress was used to expose HTTP routes from outside the cluster to services withiun the cluster.
    Created & configured ingress-service.yml to expose the pods.

3. Use of persistent storage.
    Introduced persistent volumes and configured mongo-volumes.yml.Attached the pvc file to pods so that the k8s gets the requested storage.
    pvc volumes isolates data from containers & backs it up incase a pod crashes.    