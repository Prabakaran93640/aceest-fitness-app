pipeline {
    agent any

    stages {

        stage('Run Tests in Python Container') {
            steps {
                sh '''
docker run --rm \
-v "$PWD:/app" \
-w /app \
python:3.11 \
sh -c "
pip install -r requirements.txt &&
pip install pytest &&
pytest
"
'''
            }
        }

        stage('SonarQube Scan') {
            steps {
                sh '''
docker run --rm \
-e SONAR_HOST_URL=http://host.docker.internal:9000 \
-e SONAR_TOKEN=sqa_7f9788c6c41290727cf4616d5b16a7b1507e8829 \
-v "$PWD:/usr/src" \
sonarsource/sonar-scanner-cli \
-Dsonar.projectKey=ACEest-Fitness-App \
-Dsonar.sources=.
'''
            }
        }

        stage('Build App Docker Image') {
            steps {
                sh 'docker build -t aceest-app .'
            }
        }
    }
}