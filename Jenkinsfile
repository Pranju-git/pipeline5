pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/pranjali/Documents/Devops-software/apache-maven-3.9.6/bin/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/pipeline5.war /home/pranjali/Documents/Devops-software/apache-tomcat-9.0.85/webapps'
			}}	
}}
