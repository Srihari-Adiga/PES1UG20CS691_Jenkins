pipeline {
    agent none
    stages {
        stage('Build') {
            steps {
                sh "g++ newfile.cpp -o outputfile"
                build job: "PES1UG20CS691-1"
            }
        }
        stage('Test') {
            steps {
                sh "./outputfile"
          }
        }
    }
     post {
            failure {
                node ('master')
                {
                    echo "pipeline failed"
                }
            }
        }
}
