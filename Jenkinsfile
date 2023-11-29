pipeline {
    agent any
    tools{
        maven 'maven_3_9_5'
    }
     stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Baasandorj-L/Devops-Automation.git']]])
                bat 'mvn clean install'
            }
        }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Baasandorj-L/Devops-Automation.git']]])
                bat 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    bat 'docker build -t baasandorj3036/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{pipeline {
    agent any
    tools{
        maven 'maven_3_9_5'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Baasandorj-L/Devops-Automation.git']]])
                bat 'mvn clean install'
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    bat 'docker build -t baasandorj3036/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'dockerhub-pwd', variable: '123456789')]) {
                   bat 'docker login -u baasandorj3036 -p 123456789'
                   }
                   bat 'docker push baasandorj3036/devops-integration'
                }
            }
        }
        stage('Deploy to k8s'){
            steps{
                script{
                    kubernetesDeploy (configs: 'deploymentservice.yaml', kubeconfigId: 'config33')
                }
            }
        }
    }
}
                   bat 'docker login -u baasandorj3036 -p 123456789'
                   bat 'docker push baasandorj3036/devops-integration'
                }
            }
        }
        stage('Deploy to k8s'){
            steps{
                script{
                   bat 'docker login -u baasandorj3036 -p 123456789' 
                }
            }
        }
    }
}
