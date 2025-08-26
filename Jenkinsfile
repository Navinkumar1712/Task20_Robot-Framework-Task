pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Navinkumar1712/Task20_Robot-Framework-Task.git'
            }
        }
        stage('Install Requirements') {
            steps {
                // Install Python packages from requirements.txt
                // Ensure pip is upgraded first
                bat '"C:\\Users\\Navin Kumar\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m pip install --upgrade pip'
                bat '"C:\\Users\\Navin Kumar\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m pip install -r requirements.txt'
            }
        }
        stage('Run Robot Framework Tests') {
            steps {
                // Run all tests in TestCodes folder and generate reports in Reports folder
                bat '"C:\\Users\\Navin Kumar\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" -m robot --outputdir Reports TestCodes'
            }
        }
        stage('Publish Robot Framework Reports') {
            steps {
                // Use Robot Framework Jenkins plugin if installed
                robot outputPath: 'Reports'
            }
        }
    }
}

