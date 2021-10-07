pipeline{
  agent any
  stages{
    #stage('checkout') {
    #  steps{
    #   sh 'mkdir timetracker'
    #   sh 'cd timetracker'
    #   sh 'git clone 'https://github.com/naseercs91/time-tracker.git''
    # }
    }
    stage('build'){
      steps{
        sh 'mvn compile'
        sh 'mvn clean package'
       }
    }
    stage('deploy'){
      steps{
        sh 'cp /home/slave3/workspace/JenkinDemoProj/web/target/time-tracker-web-0.5.0-SNAPSHOT.war /opt/tomcat10/webapps'
        sh '/opt/tomcat10/bin/.startup.sh'
      }
    }      
  }
}
#testing jenkins
