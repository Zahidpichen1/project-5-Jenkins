pipeline {
    agent any

    environment {
        PYTHON_ENV = 'venv'        // Virtual environment for python
    }

    stages {
        // Stage 1 : Clone the repository
        stage('checkout') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main' , url: 'https://github.com/prathoseraaj/my-python-app.git'
            }
        }

        // Stage 2 : Set up the python environment
        stage('setup Environment'){
            steps{
                echo 'Setting up python virtual environment...'
                bat '''
                   python -m venv %PYTHON_ENV%
                   call %PYTHON_ENV%\\Scripts\\activate.bat
                   pip install -r requirements.txt
                '''  
            }
        }

        // Stage 3 : Run unit tests
        stage('Run Tests') {
            steps{
                echo 'Running unit tests...'
                bat '''
                   call %PYTHON_ENV%\\Scripts\\activate.bat
                   pytest tests/
                '''   
            }
        }

        // Stage 4 : Deploy (this could be to a local HTTP server, for example)
        stage('Deploy'){
            steps{
                echo 'Deploying application...'
                // In this example, we will simulate deployment by copying the code to a server directory
                bat '''
                   xcopy /E /I /Y * C:\\path\\to\\local\\http\\server\\root\\
                '''
            }
        }
    }

    post{
        always {
            echo 'Cleaning up workspace...'   
            cleanWs()                                                         // clean the workspace after the pipeline finish
        }
        success{
            echo 'Pipeline completed successfully!'
        }
        failure{
            echo 'Pipeline failed!'
        }
    }
}
