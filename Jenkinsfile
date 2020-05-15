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
        
        stage('test results'){
            input {
                message "Do you want Test Results?"
            }
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
    }
}

