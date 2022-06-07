#! groovy
pipeline
{
  agent any
  stages
  {
    stage("deploy development")
    {
      when
      {
        expression { env.BRANCH_NAME == 'development' }
      }
      steps 
      {
        script
        {
          sh "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@15.206.82.124 '/home/deepu/deployment.sh'"
        }
      }
    }
    stage("deploy master")
    {
      when
      {
        expression { env.BRANCH_NAME == 'master' }
      }
      steps
      {
        script
        {
         sh "ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@13.234.38.247 '/home/deepu/deployment.sh' "
        }
      }
    }
  }
}
