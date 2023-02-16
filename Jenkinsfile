pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                catchError{
                    sh "g++ newfile.cpp -o outputfile"
                    build job: "PES1UG20CS691-1"
                }
                
            }
        }
        stage('Test') {
            steps {
                catchError
                {
                   sh "./outputfile"
                }
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
