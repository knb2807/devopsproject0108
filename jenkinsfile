pipeline {

    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/knb2807/devopsproject0108.git'
            }
        }

        stage('Build Image') {
            steps {
                sh 'docker build -t website:v1 .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f website || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 80:80 --name website website:v1'
            }
        }

    }

}
