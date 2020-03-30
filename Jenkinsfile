pipeline {
    agent any
	Tools{
		jdk 'jdk1.8.0_241'
		maven 'apache-maven-3.6.3'
	}
    stages {
        stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/adityaswarup241/java-war.git"
            }
    	}
	stage ('Build') {
	    steps {
		rtMavenRun(
		  bat 'mvn clean install'
		  )
		}
	}
	stage ('Deploy'){
	    steps {
		copy C:\Users\zaya\.jenkins\workspace\git-job\target\*.war C:\Users\zaya\apache-tomcat-8.5.53\webapps
		cd C:\Users\zaya\apache-tomcat-8.5.53\bin
		start startup.bat
		}
	}
	}
	}



		   
