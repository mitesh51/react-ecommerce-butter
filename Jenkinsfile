pipeline {
//  agent any
//	agent {
//		kubernetes {
		  //label 'maven'  // all your pods will be named with this prefix, followed by a unique id
	//	  idleMinutes 5  // how long the pod will live after no jobs have run on it
	//	  yamlFile 'build-agent-pod.yaml'  // path to the pod definition relative to the root of our project 
		//  defaultContainer 'maven'  // define a default container if more than a few stages use it, will default to jnlp container
	//	}
		agent {
	        node {
        label 'myVM'

    }
	}  
  
	stages {
		stage('UnitTests & Coverage') {
			steps {
        echo "Unit Tests" 
      }		
		}
		stage('Static Code Analysis') {

			steps {
        echo "SCA"
			}
		}
    
		stage('Build') {
			steps {
				echo "Build"
				//archiveArtifacts(artifacts: 'dist', onlyIfSuccessful: true, fingerprint: true)
			}
		}
		stage('Docker Image') {
			steps {
        echo "Docker Image"
			}
		}
 		stage('EKS-Deployment') {
			steps {
				//kubernetesDeploy configs: 'eks-deployment.yaml', kubeConfig: [path: ''], kubeconfigId: 'eks-kubeconfig', secretName: '', ssh: [sshCredentialsId: '*', sshServer: ''], textCredentials: [certificateAuthorityData: '', clientCertificateData: '', clientKeyData: '', serverUrl: 'https://']
			  echo "GKE-Deployment"
      }
		}
	}
}
