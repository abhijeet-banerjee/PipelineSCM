pipeline
{
agent any
tools
{
maven "Maven 3.6.3"
}
stages
{
stage('Build')
{
steps
{
bat "mvn clean"
}
}

stage('Test')
{
steps
{
bat "mvn test"
}
}

stage('Deploy')
{
steps
{
bat "mvn package"
}
}

}                      // stages end here.
  
 // post operation performed
  post
  {
    cleanup
    {
      dir("${workspace}@tmp")
      {
        deleteDir();
      }
       dir("${workspace}@script")
      {
        deleteDir();
      }
    }
  }
  
}

