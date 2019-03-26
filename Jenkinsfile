pipeline {
    agent any
     environment {
    PATH = "/vol_c/richy/sratoolkit.2.9.2-centos_linux64/bin/:$PATH"
  }
    stages {
        stage("Interactive_Input") {
            steps {
                script {
                def userInput = input(
                 id: 'userInput', message: 'Enter the cart file:?', 
                 parameters: [
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Name of cart file', name: 'Cartfile'],
                 [$class: 'TextParameterDefinition', defaultValue: 'None', description: 'Test Info file', name: 'Test']
                ])
                echo ("Cart file requested: "+userInput['Cartfile'])
                //sh 'export PATH=/vol_c/richy/sratoolkit.2.9.2-centos_linux64/bin:$PATH'
                //sh 'export PATH="$PATH:/vol_c/richy/sratoolkit.2.9.2-centos_linux64/bin'
                sh 'echo $PATH'
                //sh 'prefetch -o kart cart_DAR51523_201901081846.krt' failed jenkins 35
                //sh 'prefetch -o kart cart_DAR51522_201901081909.krt' failed jenkins 40 phs000915.v1.p1.c2\Dataintegraterd_phs000915.v1.p1
                  //phs000915.v1.p1.c2\RNAseq_
                  //sh 'prefetch -o kart cart_DAR51524_201901081852.krt'
                  //sh 'prefetch -o kart cart_DAR51524_201901081853_t.krt'  
                  //sh 'prefetch -o kart cart_DAR51524_201901081853.krt'  
                  sh 'prefetch -o kart cart_DAR51524_201901081854.krt'  

                }
            }
        }
        stage('PreFetch') {
            steps {
                echo 'Finding cartfiles..'
                
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
