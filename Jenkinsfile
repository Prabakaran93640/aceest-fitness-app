pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt || pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest || python -m pytest'
            }
        }

        stage('SonarQube Scan') {
            steps {
                sh '''
docker run --rm \
-e SONAR_HOST_URL=http://host.docker.internal:9000 \
-e SONAR_TOKEN=YOUR_TOKEN \
-v "$PWD:/usr/src" \
sonarsource/sonar-scanner-cli \
-Dsonar.projectKey=ACEest-Fitness-App \
-Dsonar.sources=.
'''
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t aceest-app .'
            }
        }
    }
}