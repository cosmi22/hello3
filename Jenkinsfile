pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                jiraComment body: 'This comment was sent from Jenkins pipeline. Reverted to initial state', issueKey: 'TES-7'
            }
        }
    }
}
