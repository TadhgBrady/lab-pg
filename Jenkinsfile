pipeline {
	agent "none"
	stages {
		stage("Checkout") {
			agent {label "nginx_tst1"}
			steps{
				echo "Stage 1- Checkout"
				git 'https://github.com/TadhgBrady/lab-pg.git'
				sh 'git checkout master'
				sh 'git branch'
				sh "pwd"
				sh "ls"
			}
		}
		stage("Copy Files to Nginx") {
			agent {label "nginx_tst1"}
			steps {
				sh "cp -r * /usr/share/nginx/html"
			}
		}
		stage("Copy Files to python") {
			agent {label "python_tst1"}
			steps {
			    	echo "Stage 1- Checkout"
				git 'https://github.com/TadhgBrady/lab-pg.git'
				sh 'git checkout build-2'
				sh 'git branch'
				sh "pwd"
				sh "ls"
			
			}	
		}	
		stage("python server") {
			agent {label "python_tst1"}
			steps { 
			    dir("server"){
				sh "python./server.py"
			    }
			}	
		}
	}
}