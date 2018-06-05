pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage "Validate types" {
            steps {
                sh "./node_modules/.bin/flow"
            }
        }
        stage "Test and validate" {
            steps {
              sh "npm install gulp-cli && ./node_modules/.bin/gulp"
              junit 'reports/**/*.xml'
            }
        }
        stage "Cleanup" {
            steps {
                deleteDir()
            }
        }
    }
}
