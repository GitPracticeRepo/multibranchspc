pipeline{
    agent any
    stages {
        stage('SCM') {
            git 'https://github.com/GitPracticeRepo/multibranchspc.git'
        }

        stage('Build and postbuild'){
            sh 'mvn package'
            archiveArtifacts 'target/*.jar'
            junit 'target/surefire-reports/*.xml'
        }
    }
}

