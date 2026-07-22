pipeline {
  agent any
  tools { 
        maven 'Maven'  
    }
   stages{
    stage('CompileandRunSonarAnalysis') {
            steps {	
		bat 'mvn clean verify sonar:sonar -Dsonar.projectKey=samplebugwebapp -Dsonar.organization=SampleBugWebApp -Dsonar.host.url=https://sonarcloud.io -Dsonar.token=74e68cdc781833a09346c31f563ccbf67b18792f'
			}
    }

/*	stage('RunSCAAnalysisUsingSnyk') {
           steps {		
				withCredentials([string(credentialsId: 'SNYK_TOKEN', variable: 'SNYK_TOKEN')]) {
					sh 'mvn snyk:test -fn'
				}
			}
    } */		
  }
}
