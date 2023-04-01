pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                jiraComment body: 'This comment was sent from Jenkins pipeline. Testing deployments', issueKey: 'TES-7'
            }
        }
    }
}
