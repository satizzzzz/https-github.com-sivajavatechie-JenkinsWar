#!/bin/groovy
def tomcatWeb = "E:\\Apache Software Foundation\\Tomcat 9.0\\webapps"
def tomcatBin = "E:\\Apache Software Foundation\\Tomcat 9.0\\bin"
def mvnHome = 'tool' name:'Maven', type:'maven'

pipeline {
      agent any
    stages{  
        stage('git checkout') {
            steps {
                git "https://github.com/satizzzzz/https-github.com-sivajavatechie-JenkinsWar.git"
            }
        }
        stage('Building War'){
            steps {
                
                bat "${mvnHome}/bin/mvn package"
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
