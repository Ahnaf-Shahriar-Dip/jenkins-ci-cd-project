pipeline {
    agent any // This tells Jenkins to allocate any available agent (worker node) to run the pipeline.

    stages {
        // Stage 1: Get the latest code from the GitHub repository
        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
                git branch: 'main', 
                url: 'https://github.com/Ahnaf-Shahriar-Dip/jenkins-ci-cd-project.git'
                // This step clones your public repository. No credentials are needed.
            }
        }

        // Stage 2: A simulated build stage
        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'echo Running build commands on Windows...'
                bat 'dir' // This Windows command lists the files in the current directory, proving the code was checked out.
            }
        }

        // Stage 3: A simulated test stage
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo Running unit tests...'
                // In a real project, you would run commands like: bat 'npm test' or bat 'python -m pytest'
            }
        }

        // Stage 4: A simulated deployment stage
        stage('Deploy') {
            steps {
                echo 'Deploying to environment...'
                bat 'echo Simulating deployment to a server'
            }
        }
    }

    // This post section runs after all stages are completed, regardless of success or failure.
    post {
        always {
            echo 'Pipeline for jenkins-ci-cd-project has completed.'
            bat 'echo This always runs. Good for cleanup.'
        }
        success {
            echo 'Pipeline succeeded! 🎉'
            // You can add notifications here (e.g., email, Slack)
        }
        failure {
            echo 'Pipeline failed! ❌'
            // You can add notifications for failure here
        }
    }
}
