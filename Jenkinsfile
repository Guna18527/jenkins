pipeline {
    agent any
    
    tools {
        maven 'maven3'
    }

    stages {
        stage('git checkout') {
            steps {
                git 'https://github.com/Guna18527/jenkins.git'
            }
        }
        stage('maven') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('echo') {
            steps {
                echo 'completed'
            }
        }
    }

    post {
        always {
            echo 'post build action'
            build job: 'python'
            build job: 'maven project'
        }
    }
}
