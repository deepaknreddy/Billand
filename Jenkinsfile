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
          sh 'ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@3.111.198.170 "/home/deepu/deployment.sh"'
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
         sh 'ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/.ssh/id_rsa deepu@3.6.88.34 "/home/deepu/deployment.sh"'
        }
      }
    }
  }
}
