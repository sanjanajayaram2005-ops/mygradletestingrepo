pipeline{
  agent any

  tools{
    jdk 'jdk'
  }
  stages{
    stage ('Checkout')
    {
      steps
      {
        git branch : 'master' , url : 'https://github.com/sanjanajayaram2005-ops/mygradletestingrepo.git'
      }
    }
    stage ('Build')
    {
      steps
      {
        sh 'chmod x+ gradlew'
        sh './gradlew build'
      }
    }
    stage ('Test')
      {
        steps
      {
        sh './gradle test'
      }
      }
      stage ('Run')
      {
        steps
        {
          sh './gradle run'
        }
      }
    }
  post
  {
    success
    {
      echo "Build success"
    }
    failure
    {
      echo "Build failed"
    }
  }
}
    
        
