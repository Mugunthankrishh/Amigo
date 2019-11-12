pipeline {
   agent any
   parameters {
        choice(choices: ['dev', 'prod'], description: 'What AWS region?', name: 'region')
    }
   
   stages {
        stage('Build') {
           
            steps {
                echo 'Building..'
                 sh 'mvn package'
                 script {
              timeout(time: 10, unit: 'MINUTES') {
                input(id: "Deploy Gate", message: "Deploy ${params.project_name}?", ok: 'Deploy')
              }
            }
        }
        }
   
        stage('Deploy') {
           
            steps {
                
                sh 'sudo apt update -y'
                sh 'sudo apt install tomcat8 -y'
                sh 'sudo apt install tomcat8-admin -y'
                sh 'sudo apt install tomcat8-user -y'

            }
        }
    }
}
