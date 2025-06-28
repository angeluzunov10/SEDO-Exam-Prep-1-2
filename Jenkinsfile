// pipeline {
//     agent any

//     stages {
//         stage('Checkout') {
//             steps {
//                 checkout scm
//             }
//         }

//         stage('Restore dependencies') {
//             steps {
//                 bat 'dotnet restore'
//             }
//         }

//         stage('Build') {
//             steps {
//                 bat 'dotnet build --no-restore'
//             }
//         }

//         stage('Test') {
//             steps {
//                 bat 'dotnet test --no-build --verbosity normal'
//             }
//         }
//     }
// }


pipeline {
    agent any

    stages {
        stage('Checkout') {
			when {
				anyOf {
					branch 'develop'
					branch 'main'
				}
			}
			
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
			when {
				anyOf {
					branch 'develop'
					branch 'main'
				}
			}
			
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build') {
			when {
				anyOf {
					branch 'develop'
					branch 'main'
				}
			}
			
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Test') {
			when {
				anyOf {
					branch 'develop'
					branch 'main'
				}
			}
			
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
