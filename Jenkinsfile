pipeline{
    agent any
    tools{
        maven "3.6.3"
    }
    stages{
        stage('Source') {
            steps{
                git branch: 'main', url: 'https://github.com/MoussaPana/ProjetSIR2022.git'
            }
        }
        stage ('Build') {
            steps{
                sh 'mvn clean org.jacoco:jacoco-maven-plugin:prepare-agent install'
            }
        }
        stage ('SonarQube Analysis') {
            steps{
                sh 'mvn sonar:sonar'
            }
        }

    } // stages



}
