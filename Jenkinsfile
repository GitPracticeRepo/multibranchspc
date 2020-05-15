pipeline{
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    paramters{
        string(name: 'MVNGOAL', defaultValue: 'package')

        string(name: 'ARTIFACTPATH', defaultValue: 'target/*.jar')
    }
    stages {
        stage('scm Build' ){
            steps {
                git 'https://github.com/GitPracticeRepo/multibranchspc.git'
                sh "mvn ${params.MVNGOAL}"
                archiveArtifacts "${params.ARTIFACTPATH}"
                

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

