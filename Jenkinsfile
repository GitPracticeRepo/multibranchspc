pipeline{
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('scm Build and postbuild'){
            steps {
                git 'https://github.com/GitPracticeRepo/multibranchspc.git'
                sh 'mvn package'
                archiveArtifacts 'target/*.jar'
                junit 'target/surefire-reports/*.xml'

            }
            
        }
    }
}

