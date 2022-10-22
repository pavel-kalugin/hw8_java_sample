pipeline {
      agent any

       tools {
          maven 'maven 3.8.6'
        }

       stages {
           stage("Test") {
              steps{
               sh 'mvn --version'
              }
           }

           stage("Test") {
             steps{
                sh 'mvn clean package'
             }
          }
       }
   }
