pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                 jiraSendDeploymentInfo environmentId: '', environmentName: '', environmentType: 'development', issueKeys: ['TES-7'], serviceIds: [''], site: 'cosmi.atlassian.net', state: 'unknown'
            }
            
            post {
                success {
                    // Trigger a deployment in Jira when the build succeeds
                    jiraDeploymentUpdate(
                        idOrKey: 'TES-7',
                        versionName: '1.0',
                        environment: 'Production',
                        comment: 'Deployment succeeded'
                    )
                }
                
                failure {
                    // Trigger a deployment failure in Jira when the build fails
                    jiraDeploymentUpdate(
                        idOrKey: 'TES-7',
                        versionName: '1.0',
                        environment: 'Production',
                        comment: 'Deployment failed'
                    )
                }
            }
        }
    }
}
