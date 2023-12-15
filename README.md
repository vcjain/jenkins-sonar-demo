# jenkins SoanrQube Demo


## Using Sonar Cloud

URL : https://sonarcloud.io/login

- Login through your GitHub account
- Navigate to MyAccount --> Organization
- Create a new Organization
- Navigate to Security Tab
- Generate a new Token
- Add secret text Token as Credential in the Jenkins


## Configuring Sonar in the Jenkins

- Add Sonar scanner plugin in Jenkins
- Setup SonarServer in the Systems in Jenkins
-  -  Check Environment Variable

## Trobleshooting: 
-If you are not able to get your analysis on SonarQube Dashboard, then try to create your a project In SonarQube with some name and key and use same key in your jenkinsfile. 
