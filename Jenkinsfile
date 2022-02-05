pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build2'
                sh 'mkdir build2'
                sh 'touch build2/test.txt'
                sh 'echo "Akash" >> build2/test.txt'
                sh 'echo "Sanjay" >> build2/test.txt'
                sh 'echo "Ghode" >> build2/test.txt'
            }
        }
        stage('Test') {
            steps {
                sh 'test -f build2/test.txt'
                sh 'grep "Akash" build2/test.txt'
                sh 'grep "Sanjay" build2/test.txt'
                sh 'grep "Ghode" build2/test.txt'
                
            }
        }
        stage('Publish') {
            steps {
                archiveArtifacts artifacts: 'build2/'
            }
        }
        
    }
}
