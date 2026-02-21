pipeline{
    agent any

    stages {
        stage('Restore dependencies') {
            when{
                expression{
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                echo 'Restoring dependencies'
                bat 'dotnet restore'
            }
        }

        stage('Build Project') {
            when{
                expression{
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                echo 'Build project'
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test Project') {
            when{
                expression{
                    return env.GIT_BRANCH == 'origin/main'
                }
            }
            steps{
                echo 'Test project'
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}