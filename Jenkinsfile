pipeline{
    agent any
    stages{
	stage('SCA-->Snyk') {
            agent any
            steps{
				checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/charankk21/TruffleTest.git']]])
				snykSecurity failOnIssues: false, organisation: '35c65e0d-af9d-4ed5-9caf-db0821e2f219', snykInstallation: 'snykKey', snykTokenId: 'snykSecrectS'
                }
        }
stage('snyk-jira') {
		steps {
			script{
				catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') 
				{
					bat 'hrdfhd --orgID=fdhadfh --token=fhadf --jiraProjectKey=qgfdahd --configFile=true --jiraTicketType=Task --projectID=cbdsfghdf'
					bat 'exit 0'
				}
			}
		}
	}
        stage ('DAST-->ZAP')
                {
			agent any
    			steps
                               {
         			bat 'java -jar geasehgad -quickurl gfdhafdsh -quickout C:\\result_1.html -quickprogress -cmd'
    				}
		}
	stage('SAST-->SonarQube')
		{
			agent {label 'linagent'}
			options { skipDefaultCheckout()     }
	                steps{
                                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE')  {
				sh 'echo hello'
				deleteDir()
				sh 'sudo git clone https://github.com/charankk21/SonarQube.git'
				dir('SonarQube'){
				sh 'mvn sonar:sonar -Dsonar.projectKey=qgfdeaadhg -Dsonar.host.url=fdsghdf -Dsonar.login=qwgasdg'
				sh 'exit 0'
				}
			}
    		}
	}
	}
}