pipeline{

	agent none
	stages{
	    stage('Non-Parallel stage'){
		    agent {
			    label 'master'
			    }
			
		steps{
			echo "This stage will execute first";
			}
	}

	stage('Run Tests'){
		parallel {
		
			stage('Run on Windows agent'){
			
			agent {
				label 'Windows_Node';
				}
				steps{
				
				echo "RUNNING ON WINDOWS_NODE ,i.e, AGENT";

				}
		}
			
			
			stage('Run on master'){
			
			agent{
				label 'master';
				}
				
				steps{
				echo "RUNNING ON THE MASTER";
				}
		}
	}
	}
	}

}
