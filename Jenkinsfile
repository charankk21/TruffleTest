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
					bat 'C:\\Users\\Administrator\\Downloads\\snyk-jira-sync-win.exe --orgID=35c65e0d-af9d-4ed5-9caf-db0821e2f219 --token=e6cab6a7-1edb-4c11-83f7-8fc1055080e4 --jiraProjectKey=SNYK --configFile=true --jiraTicketType=Task --projectID=d9ec6f75-6b7e-4d9f-bc43-305ea2463b56'
					bat 'exit 0'
				}
			}
		}
	}
	}
}