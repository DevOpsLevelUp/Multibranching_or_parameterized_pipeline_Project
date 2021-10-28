pipeline {
    agent any
    tools{
        jdk 'JDK'
        
    }
    stages {
        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonarqube') {
                    sh "./gradlew sonarqube"
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
        stage('BUILD') {
            steps {
                echo 'BUILD OF Project IN PROGRESS'
                sleep(3)
            }
        }
        stage('PACKAGE & DEPLOY') {
            steps {
                echo 'PACKAGING and DEPLOYMENT IN PROGRESS'
                sleep(3)
            }
        }
        stage('POST DEPLOYMENT TESTs') {
            steps {
                echo 'POST DEPLOYMENT TEST PHASE IN PROGRESS'
                sleep(3)
            }
        }
        stage('ARCHIVE') {
            steps {
                echo 'ARCHIVING PHASE IN PROGRESS'
                sleep(3)
            }
        }
    }
}
