pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Blaisekilang4851/LSA-Capstone-Project-Continuous-Intergration-Continuous-Development.git']])
            }
        }
         stage('Test') {
            steps {
                git branch: 'main', url: 'https://github.com/Blaisekilang4851/LSA-Capstone-Project-Continuous-Intergration-Continuous-Development.git'
                sh 'python3 Python1.py'
            }
        }
         stage('Deploy') {
            steps {
                sh 'python3 -m Python1'
                echo 'Deploy code'
            }
        }
    }
    post {
        success {
               mail bcc: '', body: '''Build has been successful. Refer to the link for an insight 
                    https://github.com/jasminejack12345/ann.git''', cc: '', from: '', replyTo: '', subject: 'CI/CD Pipeline', to: 'jasmineejack@gmail.com, jahno743@gmail.com, blaisekilang4@gmail.com, lukeceit57@gmail.com'          
        }
        failure {
            mail bcc: '', body: 'A certain stage in the bulild has failed checkout SCM at https://github.com/Blaisekilang4851/LSA-Capstone-Project-Continuous-Intergration-Continuous-Development.git', cc: '', from: '', replyTo: '', subject: 'CI/CD pipeline Build has failed,', to: 'anneludemejay@gmail.com, jahno743@gmail.com, blaisekilang4@gmail.com, lukeceit57@gmail.com'
           }
       }
}         
