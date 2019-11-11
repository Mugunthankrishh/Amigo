pipeline {
      agent { label 'ubuntu' }
    stages {
        stage('Build') { 
            steps {
                   sh 'mvn package'
                // 
            }
        }
        stage('Test') { 
            steps {
                   echo 'Run integration tests here...'
                // 
            }
        }
        stage('Deploy') { 
            steps {
                  echo 'Deploy...'
                // 
            }
        }
    }
}
