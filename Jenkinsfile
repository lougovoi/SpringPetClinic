pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('Checkout'){
            steps{
                git branch: 'main',
                url: 'https://github.com/lougovoi/SpringPetClinic.git'
            }
        }
        stage('Building'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Testing'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeLine/target/*.jar'
            }
        }
    }
}
