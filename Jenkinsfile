pipeline {
        agent none
        stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('SonarQube Scanner') {
                sh 'mvn clean package sonar:sonar'
              }
            }
          }
         
        }
      }
