pipeline{
    agent any
    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['staging', 'production'],
            description: 'Where to deploy'
        )
    }   
    
     
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