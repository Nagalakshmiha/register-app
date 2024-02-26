pipeline {
    agent {
        label 'Jenkins_Agent'
    }
    tools {
        jdk 'java17'
        maven 'maven3'
    }
    stages {
        stage("Cleanup Workspace") {
            steps {
                cleanWs()
            }
        }
        stage("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/Nagalakshmiha/deveops-projects'
            }
        }
        stage("Build Application") {
            steps {
                sh "mvn clean package"
            }
        }
        stage("Test application") {
            steps {
                sh "mvn test"
            }
        }
    }
}
