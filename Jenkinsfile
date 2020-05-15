pipeline{
    agent any
    stages {
        stage('scm Build and postbuild'){
            git 'https://github.com/GitPracticeRepo/multibranchspc.git'
            sh 'mvn package'
            archiveArtifacts 'target/*.jar'
            junit 'target/surefire-reports/*.xml'
        }
    }
}

