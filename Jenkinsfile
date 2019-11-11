properties([
pipelineTriggers([pollSCM('H/3 * * * *')])
])

node(){
cleanWs()
stage("checkout"){
checkout scm
}

stage("make"){
sh "make"
sh "./main"
}
stage("artifact"){
archiveArtifacts artifacts: 'main'
}

}
