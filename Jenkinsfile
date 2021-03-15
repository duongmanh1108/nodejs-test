pipeline {
     agent any
     stages {
          stage("Clone stage") {
               steps {
                    git 'https://github.com/duongmanh1108/nodejs-test.git'
               }
          }
          stage("Build stage") {
               steps {
                    sh 'npm install'
                    sh 'nohup node index.js &'
                    sh 'npm test'
               }
          }
     }
     post {
          always {
               emailext body: '${DEFAULT_CONTENT}', subject: '${DEFAULT_SUBJECT}', to: 'duongmanh1108@gmail.com'
          }
          success {
               sh 'docker build -t nodejs-test .'              
          }
     }
}
