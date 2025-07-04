pipeline {
    agent any
    tools {
        maven 'MyMaven'
    }
    stages{
        
        stage('checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vcjain/jenkins-sonar-demo.git']])
            }    
        }
        stage('Build'){
            steps{
                echo 'Building Maven project'
                script{
                    if(isUnix()){    
                        sh 'mvn clean compile'
                    }else{
                        bat 'mvn clean compile'
                    }
                }
            }
        }
        stage('Test'){
            steps{
                echo 'Building Maven project'
                
                script {
                    if (isUnix()){
                        sh 'mvn test'
                    }else{
                        bat 'mvn test'
                    } 
                }
                junit '**/target/surefire-reports/*.xml'
                jacoco classPattern: '**/target/classes', exclusionPattern: '**/*Test*.class', execPattern: '**/target/jacoco.exec', inclusionPattern: '**/*.class', sourceExclusionPattern: 'generated/**/*.java', sourceInclusionPattern: '**/*.java'
            }
        }
        stage('SonarQube Analysis'){
            steps{
                echo 'Scanning Maven project'
                withCredentials([string(credentialsId: 'Varun-Sonar-Token', variable: 'SONAR_TOKEN')]) {
                    withSonarQubeEnv(installationName: 'Sonarcloud', credentialsId: 'Varun-Sonar-Token') { 
                        script {
                            if (isUnix()){
                                sh 'mvn sonar:sonar -Dsonar.projectKey=varun-sonar_demo -Dsonar.organization=varun-sonar -Dsonar.host.url=https://sonarcloud.io'
                                sh 'sleep 50'
                            }else{
                                bat 'mvn sonar:sonar -Dsonar.projectKey=varun-sonar_demo -Dsonar.organization=varun-sonar -Dsonar.host.url=https://sonarcloud.io'
                                bat 'ping -n 51 127.0.0.1 > nul'
                            }
                        }
                        
                    }
                }    
            }
        }
    }
        

}
