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
                //sh 'prefetch -o kart cart_DAR51524_201901081853.krt'
                //sh 'prefetch -o kart cart_DAR51524_201901081854.krt'

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
stage("SCP to cc ubuntu")
node {
  sshagent(credentials: ['CC_ubuntu_ssh']) {
    sh 'scp -r /vol_c/richy/data/sra ritu@128.196.56.64:/media/ritu/sra_backup/NE_prostatecancer-trento_cornell_broad/RNAseq'

  }
}
        }
    }
}
