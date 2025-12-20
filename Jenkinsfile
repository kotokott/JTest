pipeline {
    agent { docker { 
        image 'maven:3.9.11-eclipse-temurin-21-alpine'
        //args '-v /root/.m2:/root/.m2'
    } }
    stages {
        stage('build') {
            steps {
                //sh 'mvn clean package -DskipTests'
                sh 'mvn -Dmaven.repo.local=.m2/repository clean package -DskipTests'
            }
        }
        stage('run') {
            steps {
                sh 'java -jar target/JTest-1.0-jar-with-dependencies.jar'
            }
        }
    }
}
