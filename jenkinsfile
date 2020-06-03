currentBuild.displayName="My-Project-#"+currentBuild.number
pipeline{
     agent any
    stages{
         stage('Checkout-SCM')
		 {
		     steps{
		                cleanWs()
			            checkout([$class: 'GitSCM', branches: [[name: '*/master']], 
				        doGenerateSubmoduleConfigurations: false, 
				        extensions: [], 
				        submoduleCfg: [],
				        userRemoteConfigs: [[credentialsId: '2a239424-0e74-41e9-8034-488a00f90311',
			            url: 'https://github.com/chandrasekhar1897/simple-java-maven-app.git']]])
			        }
		   }
	
	      stage('Build-stage')
		 {
		    steps{
		               sh label: '', script: 'mvn package'
		                                archiveArtifacts '**/*.war'
		                                 archiveArtifacts '**/*.jar'

		             }
	     }
		   
    }
}
