pipeline{
agent any
stages{
stage('No-op'){
steps{
sh 'ls'
}
}
}
post{
always{
echo 'One way or another, I have finished'
deleteDir()
}
success{
echo 'I succeeededd!'
}
unstable{
echo 'I am unstable:/'
}
failure{
echo 'I failed:('
}
changed {
echo 'Things were different before....'
}
}
}

