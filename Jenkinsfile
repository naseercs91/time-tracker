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
        sh 'mv target/*.war target/time-tracker-web-0.5.0-SNAPSHOT.war'
       }
    }
    stage('deploy'){
      steps{
        sshagent(['tomcat'])
        ssh """
        scp -o StrictHostKeyChecking =no target/time-tracker-web-0.5.0-SNAPSHOT.war
        ubuntu@18.118.155.23:opt/tomcat10/webapps/
        ssh ubuntu@18.118.155.23 /opt/tomcat10/bin/shutdown.sh
        ssh ubuntu@18.118.155.23 /opt/tomcat10/bin/startup.sh
        """
      }
    }      
  }
}
#testing jenkins
