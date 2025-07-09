# jenkins SonarQube Demo


## Using Sonar Cloud

URL : https://sonarcloud.io/login

- Login through your GitHub account
- Navigate to MyAccount --> Organization
- Create a new Organization
- Navigate to Security Tab
- Generate a new Token. You can also give your preferred name.
- Add secret text Token as Credential in the Jenkins. (Give Id as sonar-token, to match the Jenkinsfile steps) 


## Configuring Sonar in the Jenkins

- Add Sonar scanner, Jacoco plugin in Jenkins
- Setup SonarServer in the Systems in Jenkins
-  -  Check Environment Variable
   -  Give your preferred name of SonarServer, in Jenkinsfile we will referring it. (sonarcloud)
   -  Give server url as  - https://sonarcloud.io
   -  Select token credentials that we created above
   -  

## Trobleshooting: 
-If you are not able to get your analysis on SonarQube Dashboard, then try to create your a project In SonarQube with some name and key and use same key in your jenkinsfile. 


# Analyze your project with GitHub CI
## Create GitHub Secrets
In your GitHub repository, go to Settings > Secrets and variables > Actions and create the following new secrets:
- Click on New repository secret.
- In the Name field, enter
```
SONAR_TOKEN
```
- In the Value field, enter an existing token, or a newly generated one.
- Click on Add secret.
##
- Click on New repository secret.
- In the Name field, enter
```
SONAR_HOST_URL
```
- In the Value field, enter
```
http://localhost:9000
```
- Click on Add secret.
  
## Create Workflow YAML File
  
