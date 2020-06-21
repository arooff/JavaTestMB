
#!groovy
// Check ub1 properties
properties([disableConcurrentBuilds()])

pipeline {
    agent { 
        label 'master'
        }
    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
    stages {
        stage("First step") {
            steps {
                sh 'ssh pi@rasp \'hostname\''
            }
        }
        stage("Second step") {
            steps {
                sh 'javac HelloWorld.java'
                sh 'java HelloWorld'
                sh 'echo \'Finished\''
            }
        }
    }
}
