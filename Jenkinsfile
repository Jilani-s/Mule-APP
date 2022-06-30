pipeline {
        agent none
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv(credentialsId: 'sqj') {
    sonar.projectKey=com.mycompany:mule4-batch-demo
sonar.host.url=http://44.197.198.219:9000/
sonar.login=abfd7b79ef38ab571e685d5e77d5f26d298c1f19
sonar.login=admin
sonar.password=admin@123
sonar.sources=/var/lib/jenkins/workspace/Mule-APP
}
            }
          }
          stage("Quality Gate") {
            steps {
              timeout(time: 1, unit: 'HOURS') {
                waitForQualityGate abortPipeline: true
              }
            }
          }
        }
      
