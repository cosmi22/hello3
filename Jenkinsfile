pipeline {
    agent any
    
    stages {
        stage('Deploy') {
            steps {
                 echo 'Hello World'
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
