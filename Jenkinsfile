pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps {
                checkout scm
            }
        }
        stage('Show Files'){
            steps{
                bat 'dir'
            }
        }
        stage('Test') {
            steps {
                bat 'python -m unittest test_calculator.py -v'
            }
        }
        stage('Deploy'){
            steps{
                bat 'xcopy /Y calculator.py dist\\'
            }
        }
    }    
}