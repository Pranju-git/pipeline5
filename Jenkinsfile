pipeline {
	agent any 
	
parameters {
  choice choices: ['dev', 'QA', 'UAT'], name: 'envorment'
}
	triggers {
  pollSCM '* * * * *'
}
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
		stage('slack-notification'){
			steps {
			slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '#devops', color: 'good', message: 'this is first stack msg', teamDomain: 'student', tokenCredentialId: '918d9957-1797-407a-a9cc-658b5c8847af'	
			}}
}}
