pipeline {
    agent any
    tools {
        maven 'MAVEN_4.0.0'
    }
    options {
        timeout (time:1, unit: 'HOURS')
    }
    triggers {
        pollSCM ('* * * * *')
    }
    stages {
        stage ('SCM') {
            steps {
                git url: 'https://github.com/spring-projects/spring-petclinic.git',
                    branch: 'main'
            }   
        }
        stage ('Build and Package') {
            steps {
                sh 'mvn clean package'                
            }
                
        }
           

    }
}