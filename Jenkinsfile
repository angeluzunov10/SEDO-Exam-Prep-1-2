pipeline {
    agent any

    stages {
        stage('Check Branch') {
            when {
                anyOf {
                    branch 'main'
                    branch pattern: "feature/.*", comparator: "REGEXP"
                }
            }
            stages {
                stage('Checkout') {
                    steps {
                        checkout scm
                    }
                }

                stage('Restore dependencies') {
                    steps {
                        bat 'dotnet restore'
                    }
                }

                stage('Build') {
                    steps {
                        bat 'dotnet build --no-restore'
                    }
                }

                stage('Test') {
                    steps {
                        bat 'dotnet test --no-build --verbosity normal'
                    }
                }
            }
        }
    }
}
