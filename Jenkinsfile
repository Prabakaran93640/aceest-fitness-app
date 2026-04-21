pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Prabakaran93640/aceest-fitness-app.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'pytest'
            }
        }

        stage('SonarQube Scan') {
            steps {
                bat '''
docker run --rm ^
-e SONAR_HOST_URL=http://host.docker.internal:9000 ^
-e SONAR_TOKEN=sqa_7f9788c6c41290727cf4616d5b16a7b1507e8829 ^
-v "%cd%:/usr/src" ^
sonarsource/sonar-scanner-cli ^
-Dsonar.projectKey=ACEest-Fitness-App ^
-Dsonar.sources=.
'''
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t aceest-app .'
            }
        }
    }
}