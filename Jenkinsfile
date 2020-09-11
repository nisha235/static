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
	}
}
stage('Upload to AWS')
{
	withAWS(credentials:'aws-static') {
    // do something
    s3Upload(file:'index.html', bucket:'s23jenkins', path:'index.html')
}
}
