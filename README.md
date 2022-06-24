############## jenkins-KRD ###########################
1- Create aws_user 
2- Generate : Jeton d'API (token) for aws user 
3- Job To be triggered 
  3-a : Déclencher les builds à distance (Par exemple, à partir de scripts)
  3-b : Generate Toekn (Jeton d'authentification)


############## jenkins-AWS###########################
1- Crée pipeline "jenkins-helloworld"
2- Configuration Pipeline sur Jenkins Pipeline : 
  2-a : Pipeline => Definition (Pipeline script from SCM )
  3-b : SCM : Git
  3-c : Repository URL : Path .git from Github
  3-d : Branches to build => Branch Specifier => */main
  4- Spécifier la branche sur jenkinsfile si défferente à master :       git branch: 'main', url: 'https://github.com/limammedsaid/jenkins-helloworld'

  5- Trigger To KRD Jenkins
      stage('Trigger Jenkins KRD')
         { 
            sh label: '' , script: " curl -X POST http://aws_user:11973db63a932d25e51ed49c506c86f456@192.168.1.200:8080/job/KRDPipeline/build?token=12345678"
        }