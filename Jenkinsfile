#!/bin/groovy
def tomcatWeb = "E:\\Apache Software Foundation\\Tomcat 9.0\\webapps"
def tomcatBin = "E:\\Apache Software Foundation\\Tomcat 9.0\\bin"

pipeline {
      agent any
      tools {
        maven 'Maven 3.6.3'
    
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
               bat "${tomcatBin}\\JenkinsWar.war\\startup.bat"
           }
        }
    }
}
