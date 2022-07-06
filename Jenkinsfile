pipeline {
        agent none
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('SonarQube Scanner') {
                      sh 'mvn clean package sonar:sonar -Dsonar.host.url=http://44.197.198.219:9000/ -Dsonar.login=abfd7b79ef38ab571e685d5e77d5f26d298c1f19 -Dsonar.login=admin -Dsonar.password=admin@123 -Dsonar.sources=/var/lib/jenkins/workspace/Mule-APP '
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
}
