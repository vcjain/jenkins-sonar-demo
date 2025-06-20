# jenkins SonarQube Demo f


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
