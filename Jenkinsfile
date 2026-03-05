pipeline {
    agent { label 'java-build' }
    tools {
        maven 'maven-3.9.12'
    }
    options {
        timeout(time: 1, unit: 'HOURS')
    }
    triggers {
        pollSCM('* * * * *')
    }
    
    stages {
        stage ('SCM') {
            steps {
                git url: 'https://github.com/AmrutAnkalagi/spring-petclinic-jenkin.git',
                    branch:'main'
            }              
        }
        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

    }
}