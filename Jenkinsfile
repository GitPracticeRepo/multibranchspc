pipeline{
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('scm Build' ){
            steps {
                git 'https://github.com/GitPracticeRepo/multibranchspc.git'
                sh 'mvn package'
                archiveArtifacts 'target/*.jar'
                

            }
        }
        input {
            message "Do you want Test Results?"
        }
        stage('test results'){
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}

