pipeline{
  agent any
  stages{
    stage('checkout') {
      steps{
        sh 'mkdir timetracker'
        sh 'cd timetracker'
        sh 'git clone 'https://github.com/naseercs91/time-tracker.git''
      }
    }
    stage('compile'){
      steps{
        sh 'mvn compile'
       }
    }
    stage('package'){
      steps{
        sh 'mvn clean package'
      }
    }      
  }
}
#testing jenkins
