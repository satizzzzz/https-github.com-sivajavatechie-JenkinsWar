#!/bin/groovy
def tomcatWeb = "E:\\Apache Software Foundation\\Tomcat 9.0\\webapps"

pipeline {
      agent any
      tools {
        maven 'maven-3.6'
    
    }
    stages{  
        stage('git checkout') {
            steps {
                git "https://github.com/satizzzzz/https-github.com-sivajavatechie-JenkinsWar.git"
            }
        }
        stage('Building War'){
            steps {
                bat 'mvn package'
            }
        }
        stage('deploying War'){
            steps {
               bat "copy target\\JenkinsWar.war \"${tomcatWeb}\\JenkinsWar.war\""
           }
        }
        stage('Starting tomcat'){
            steps {
                  bat "start cmd.exe /c E:\\Apache Software Foundation\\Tomcat 9.0\\binstartup.bat"
           }
        }
    }
}
