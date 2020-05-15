node {
    stage('scm') {
        git 'https://github.com/GitPracticeRepo/multibranchspc.git'
    }
    stage('build') {
        3.times {
            println "started build ${it}"
            sh 'mvn clean package'
            println "completed build ${it}"
        }
        
    }
}