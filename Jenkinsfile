pipeline {
    agent none
    stages {
        stage('Build') {
            agent any
            steps {
                    sh "g++ newfile.cpp -o outputfile"
                    build job: "PES1UG20CS691-1"
                 }
        }
        stage('Test') {
            agent any
            steps {
                   sh "./outputfile"
          }
        }
    }
     post {
            failure {
                node('MAVEN_OPTS')
                {
                   echo 'pipeline failed'
                }
            }
        }
}
