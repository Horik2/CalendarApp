pipeline {
    agent any

    options {
        // Unikaj współbieżnych budowań
        disableConcurrentBuilds()
        
        // Pokazuj czas trwania każdego etapu
        timestamps()
    }

    environment {
        // Ustaw zmienne środowiskowe (dostosuj do swojego projektu)
        PROJECT_NAME = "FilmApp"
    }

    stages {
        // Etap 1: Pobranie kodu z repozytorium
        stage('Checkout') {
            steps {
                script {
                    echo "🔄 Pobieranie kodu z repozytorium ${PROJECT_NAME}..."
                    checkout scm
                }
            }
        }

        // Etap 2: Instalacja zależności (dostosuj do swojej technologii)
        stage('Install Dependencies') {
            steps {
                script {
                    echo "📦 Instalowanie zależności..."
                    
                    // Przykłady dla różnych technologii (odkomentuj odpowiednią sekcję):
                    
                    // Dla Node.js:
                    // sh 'npm install'
                    
                    // Dla Maven (Java):
                    // sh 'mvn clean install -DskipTests'
                    
                    // Dla Python:
                    // sh 'pip install -r requirements.txt'
                    
                    // Dla .NET:
                    // sh 'dotnet restore'
                }
            }
        }

        // Etap 3: Budowanie projektu
        stage('Build') {
            steps {
                script {
                    echo "🏗️ Budowanie projektu..."
                    
                    // Przykłady budowania:
                    
                    // Node.js:
                    // sh 'npm run build'
                    
                    // Maven:
                    // sh 'mvn package'
                    
                    // .NET:
                    // sh 'dotnet build'
                }
            }
        }

        // Etap 4: Uruchomienie testów
        stage('Test') {
            steps {
                script {
                    echo "🔍 Uruchamianie testów..."
                    
                    // Przykłady uruchamiania testów:
                    
                    // Node.js (Jest/Mocha):
                    // sh 'npm test'
                    
                    // Maven:
                    // sh 'mvn test'
                    
                    // Python pytest:
                    // sh 'pytest'
                }
            }
            
            post {
                // Zawsze generuj raport testów
                always {
                    junit '**/target/surefire-reports/*.xml' // Dla Maven
                    // archiveArtifacts artifacts: '**/test-results.xml', allowEmptyArchive: true
                }
            }
        }
    }

    post {
        // Akcje wykonane po zakończeniu pipeline'u
        always {
            echo "✅ Pipeline ${PROJECT_NAME} zakończony - status: ${currentBuild.result ?: 'SUCCESS'}"
        }
        
        success {
            slackSend(color: 'good', message: "Build ${PROJECT_NAME} #${env.BUILD_NUMBER} zakończony sukcesem!")
        }
        
        failure {
            slackSend(color: 'danger', message: "Build ${PROJECT_NAME} #${env.BUILD_NUMBER} nie powiódł się!")
        }
    }
}