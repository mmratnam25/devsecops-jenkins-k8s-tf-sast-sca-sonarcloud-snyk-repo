pipeline {
  agent any
  tools { 
        maven 'Maven'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		bat 'mvn clean verify sonar:sonar -Dsonar.projectKey=samplewebapp1 -Dsonar.organization=samplewebapp1 -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=132aa0ddeafd80b4d45e5cecacc06a5c0331b943'
			}
    }

	stage('RunSCAAnalysisUsingSnyk') {
           steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			}
    } 		
  }
}
