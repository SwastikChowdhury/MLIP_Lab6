pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh '''#!/bin/bash
                echo 'In C or Java, we can compile our program in this step'
                echo 'In Python, we can build our package here or skip this step'
                '''
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                echo 'Test Step: Creating virtual environment and running tests'

                # Create a virtual environment named mlip
                python3 -m venv mlip

                 # Activate the virtual environment
                source mlip/bin/activate

                # Upgrade pip and install required packages
                pip install --upgrade pip
                pip install pytest numpy pandas scikit-learn
                
                # Run pytest
                pytest

                # Deactivate the virtual environment
                deactivate

                echo 'pytest run completed'
                '''

            }
        }
        stage('Deploy') {
            steps {
                echo 'In this step, we deploy our project'
                echo 'Depending on the context, we may publish the project artifact or upload pickle files'
            }
        }
    }
}
