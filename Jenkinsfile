pipeline{
    agent{label 'master'}
    tools(maven 'M3')
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/AnjuMeleth/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh   'maven compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar./var/lib/jenkins/workspace/petClinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
