properties([
pipelineTriggers([pollSCM('H/3 * * * *')])
])

node(){
cleanWs()
checkout scm
sh "make"
sh "./main"
}

pipeline {
    agent any
    

    post {
        always {
            archiveArtifacts artifacts: 'build/main', fingerprint: true
        }
    }
}
