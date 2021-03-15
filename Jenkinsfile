pipeline {
     agent { label 'my-slave-01' }
     stages {
          stage("Clone stage") {
               steps {
                    git 'https://github.com/duongmanh1108/nodejs-test.git'
                    sh 'docker build -t nodejs-test .'
               }
          }
     }
}
