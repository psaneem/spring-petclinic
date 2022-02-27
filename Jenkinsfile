pipeline {

agent { node { label 'pat' } }
tools {
        maven 'maven' 
        jdk 'JDK'
    }
stages {
    stage('Run in parallel') {
     parallel {
        stage('Code validate') {
            steps {
                sh 'mvn validate'
            }
        }
        stage('Code Compile') {
            steps {
                sh 'mvn compile'
            }
        }
     }
    }
        stage('Code Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Code Package') {
            steps {
                sh 'mvn package'
            }
        
        post { 
           success { 
            junit 'target/surefire-reports/**/*.xml'
          }
    }
        
    }
}
        
        
}
