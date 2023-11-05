pipeline {
	agent any 
	
	stages {
	    stage('Checkout') {
	        steps {
			checkout scm			       
		      }}
		stage('Build') {
	           steps {
			  sh '/home/abhishek/yobandu/Declarative/mvn install'
	                 }}
		stage('Deployment'){
		   steps {
		sh 'cp target/Declarative.war /home/abhishek/apache-tomcat-9.0.82/webapps'
			}}	
}}
