pipeline {
    agent any  // Use any available Jenkins agent

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', // Replace with your branch name
                    credentialsId: 'de344b0b-23c5-4ab6-9300-7b0025de93ea', // Replace with your credential ID
                    url: 'https://github.com/Gokulprasath-N/simple_asp.net_project.git' // Replace with your GitHub URL
            }
        }
        stage('Build Project') {
            steps {
                script {
                    // Use the appropriate .NET command for your project (e.g., dotnet build, msbuild)
                    sh 'dotnet build MyProject.sln' // Replace with your project's build command
                }
            }
        }
        // Add additional stages for testing (optional)
        /*
        stage('Run Tests') {
            steps {
                // Use the appropriate test runner for your project (e.g., dotnet test, xunit)
                sh 'dotnet test MyProject.Tests --no-build' // Replace with your test command
            }
        }
        */
        stage('Publish Artifacts') {
            steps {
                archiveArtifacts '**/*.dll', '**/*.pdb' // Capture output files (adjust paths as needed)
            }
        }
    }
}