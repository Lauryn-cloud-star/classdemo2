pipeline {
    agent any
    environment {
        VENV = 'venv'
    }
    stages {
        stage('ckeckout'){
            steps {
                git branch: 'main', url:'https://github.com/Lauryn-cloud-star/classdemo2.git' // specify your git repository URL here
            }
        }
        stage('Setup Virtual Environment') {
            steps {
                sh """
                    python3 -m venv $VENV
                    . $VENV/bin/activate
                    pip install -r requirements.txt
                """
               
            }
        }
        stage('Run Tests'){
            steps {
                sh """
                    . $VENV/bin/activate
                    pytest
                """
            }
        }
    }
}