pipeline {
    agent {
        docker {
            image 'maven:3.8.1-adoptopenjdk-11' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('git repo') {
            steps {
                bat "ls -a"
                bat "rm -rf hello-world-sample-project-lolc"
                bat "git clone https://github.com/isurupathumherath/hello-world-sample-project-lolc.git"
            }
        }
        stage('clean') {
            steps {
                bat "mvn clean -f hello-world-sample-project-lolc"
            }
        }
        stage('install') {
            steps {
                bat "mvn install -f hello-world-sample-project-lolc"
            }
        }
        stage('test') {
            steps {
                bat "mvn test -f hello-world-sample-project-lolc"
            }
        }
        stage('package') {
            steps {
                bat "mvn package -f hello-world-sample-project-lolc"
            }
        }
    }
}
