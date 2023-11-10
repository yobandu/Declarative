pipeline {
	agent any
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/tom/slave-dir/apache-maven-3.9.5/bin/mvn install'
	                 }}
		stage('Deployment'){
		    steps {
			
			sh 'cp target/Declarative.war /home/tom/slave-dir/apache-tomcat-9.0.82/webapps'
			}}
		stage('slack notification'){
		    steps {
			
			slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'grras-test', color: 'green', message: 'Welcome To Slack Grras', teamDomain: 'devops', tokenCredentialId: 'test-token'
			}}
	}}
