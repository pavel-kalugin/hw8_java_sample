pipeline {
      agent any

      triggers {
        cron('0 5 * * *')

    }

       tools {
          maven 'maven 3.8.6'
        }

       stages {
           stage("Test") {
              steps{
               sh 'mvn --version'
              }
           }

           stage("Build") {
             steps{
                sh 'mvn clean package'
             }
          }
       
             steps{
               withCredentials([usernamePassword(credentialsId: 'userTestID', passwordVariable: 'userpass', usernameVariable: 'userkey')]) {
                    //sh ('echo ${dockerHubUser}')
                    // sh ('echo ${dockerHubPassword}')
                    sh('docker login -u ${dockerHubUser} -p ${dockerHubPassword}')
                    sh('docker push pavel-kalugin/hw8_java_sample:${TAG}')
                }
            }
       }
   }
