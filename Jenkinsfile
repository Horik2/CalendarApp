pipeline {
    agent any
    
    options {
        disableConcurrentBuilds()
        timestamps()
    }

    environment {
        PROJECT_NAME = "CalendarApp"  // Zmienione z FilmApp na CalendarApp
        // Upewnij się, że używasz poprawnej nazwy użytkownika GitHub
        REPO_URL = "https://github.com/Hork2/CalendarApp.git" 
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    echo "🔄 Pobieranie kodu z repozytorium ${env.PROJECT_NAME}..."
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: '*/main']],
                        userRemoteConfigs: [[url: env.REPO_URL]]
                    ])
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    echo "📦 Instalowanie zależności..."
                    // Odkomentuj odpowiednią sekcję dla Twojego projektu:
                    
                    // Node.js:
                    // sh 'npm install'
                    
                    // Maven:
                    // sh 'mvn clean install -DskipTests'
                    
                    // Python:
                    // sh 'pip install -r requirements.txt'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo "🏗️ Budowanie projektu..."
                    // Odkomentuj odpowiednią komendę:
                    
                    // Node.js:
                    // sh 'npm run build'
                    
                    // Maven:
                    // sh 'mvn package'
                    
                    // Python:
                    // sh 'python setup.py build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "🔍 Uruchamianie testów..."
                    // Odkomentuj i dostosuj ścieżki do raportów:
                    
                    // Node.js (Jest):
                    // sh 'npm test'
                    // junit '**/junit.xml' 
                    
                    // Maven:
                    // sh 'mvn test'
                    // junit '**/target/surefire-reports/*.xml'
                    
                    // Python pytest:
                    // sh 'pytest --junitxml=test-results.xml'
                    // junit '**/test-results.xml'
                }
            }
        }
    }

    post {
        always {
            echo "✅ Pipeline ${env.PROJECT_NAME} zakończony - status: ${currentBuild.result ?: 'SUCCESS'}"
        }
        
        // Usunięte slackSend, chyba że masz zainstalowany plugin Slack
    }
}
