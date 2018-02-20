pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
	stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
	stage('Store') {
            steps {
                sh 'mvn deploy'
            }
	}
	stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
	}
    }
}
