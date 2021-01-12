pipeline {
  agent any
  stages {
    stage('build') {
      environment {
        //the following needs to be set to not kill the node process
        JENKINS_NODE_COOKIE='dontkill'
        PASSWORD=credentials("example_password_1")
      }
 steps {
   
    nodejs('<npm>'){

        sh "npm install"
        // when chaning any environmental variables ( like edit the ecosystem.config.yml or change some values in the credentials section in jenkins uncomment the next line
        // sh "node_modules/pm2/bin/pm2 kill --name node_example-app"
        sh "node_modules/pm2/bin/pm2 startOrRestart ecosystem.config.yml --env production"
      }

}
     
    }
  }
}

