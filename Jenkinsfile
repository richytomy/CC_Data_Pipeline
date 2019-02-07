pipeline {
    agent any

    stages {
        stage("Interactive_Input") {
            steps {
                script {
                def userInput = input(
                 id: 'userInput', message: 'Enter the cart file:?', 
                 parameters: [
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Name of cart file', name: 'Cartfile']
                ])
                echo ("cart file requested: "+userInput['Cartfile'])

                }
            }
        }
        stage('PreFetch') {
            steps {
                sh 'prefetch -o kart /vol_c/richy/test.sra /vol_c/richy/'+userInput['Cartfile']
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
