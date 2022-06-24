node {
    stage('Clone') {
      git branch: 'main', url: 'https://github.com/limammedsaid/jenkins-helloworld'
    }
    
    stage('Build') { 
         sh label: '', script: 'javac Main.java'
    }
    stage('run') { 
         sh label: '', script: 'java Main'
    }    
    stage('Trigger Jenkins KRD')
    { 
      sh label: '' , script: " curl -X POST http://aws_user:11973db63a932d25e51ed49c506c86f456@192.168.1.200:8080/job/KRDPipeline/build?token=12345678"
     }
}