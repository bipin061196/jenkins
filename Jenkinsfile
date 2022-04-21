pipeline {
  agent {
    node {
	  label 'ntt-gs-build'
	}
  }
  
  options {
    timestamps()
  }
  
  stages {
    stage('code checkout') {
	  steps {
	    checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'bipin-github', url: 'https://github.com/bipin061196/kubernetes']]])
	  }
	}
	
	stage('build') {
	  parallel {
	    stage('First Test') {
		  steps {
		    echo 'Run Fiest Test Case'
		  }
		}
		
		stage('Second Test') {
		  steps {
		    echo 'Run Second Test Case'
		  }
		}
		
		stage('Third Tets'){
		  steps {
		    echo 'Run Third Tets Case'
			sh 'ls'
		  }
	    }
      }
    }
  }
}
