pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                jiraComment body: 'This comment was sent from Jenkins pipeline. Testing deployments', issueKey: 'TES-7'
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
