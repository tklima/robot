pipeline {
   agent {
       docker {
           image 'python:3.7.7-stretch'
           args '--network=skynet'
       }
   }

   stages {
      stage('Build') {
         steps {
            sh 'pip install -r requirements.txt'
         }
      }
      stage('Testing') {
          steps {
            sh 'robot -d ./logs tests/'
            robot 'logs'
          }
      }
   }
}
