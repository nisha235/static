pipeline
{
agent any
stages
	{
stage('build')
	{
	steps{
	sh 'echo "hello world"'
	sh '''
	echo "multiline wokrs too"
	   
	   ls -lah
	   '''
	   }
	}
	

stage('Upload to AWS')
{
	  steps {
	withAWS(region:'us-west-2',credentials:'aws-static') {
    // do something
    s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'index.html', bucket:'s23jenkins', path:'index.html')
}
}
}
}
}
