pipeline {
    agent any
	tools{
		jdk 'JAVA_HOME'
		maven 'MAVEN_HOME'
	}
	environment{
		JAVA_HOME = "C:/Program Files/Java/jdk1.8.0_241"
		MAVEN_HOME = "C:/Users/zaya/apache-maven-3.6.3"
	}
    stages {
        stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/adityaswarup241/java-war.git"
            }
    	}
	stage ('Build') {
	    steps {
		        bat 'mvn -Dmaven.test.failure.ignore=true clean install'
		}
	}
	stage ('Deploy'){
	    steps {
		bat 'xcopy \s C:/Users/zaya/.jenkins/workspace/ci-cd-pipeline/target/hello-world-war-1.0.0.war C:/Users/zaya/apache-tomcat-8.5.53/webapps/'
		bat 'cd C:/Users/zaya/apache-tomcat-8.5.53/bin'
		bat 'start startup.bat'
		}
	}
	}
	}



		   
