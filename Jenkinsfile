pipeline{
       agent any
	stages{
	   stage('Test'){
		steps{
			sh 'echo "Fail!"; exit 0'
}
}
}
post{
	always{
	   echo 'This will always Run'
	}
	success{
	 echo 'This will run only if successfull'
	}
	failure{
		echo 'This will run only if failed'
	}
	unstable{
		echo 'This will run only if the run was marked as unstable'
}
changed{
echo 'This will run only if the state of the Pipeline has changed'
echo 'For Example,If the pipeline was previously failing but is now successfull'
}
}
}
	            
