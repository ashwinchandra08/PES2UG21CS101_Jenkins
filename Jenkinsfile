pipeline { 
  agent any 
  stages {
          stages('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                          branches: [[name: '*/main']],
                          userRemoteConfigs: [[url: 'https://github.com/ashwinchandra08/PES2UG21CS101_Jenkins/Jenkins.git']]])
            }
          }
    stage ('Build') {
      steps { 
        build 'PES2UG21CS101-1'
        sh 'g++ main.cpp -o output' 
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploy' 
      }
    }
  }
post {
  failure {
    error 'Pipeline failed'
  }
}
}
