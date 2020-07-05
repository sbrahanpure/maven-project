pipeline
{
agent any
	stages
	{
	stage ( 'SCM Integrate' )
		{
		steps { git 'https://github.com/sbrahanpure/maven-project' }

		}
		
		stage ( 'Build' )
		{
		steps { withMaven(jdk: 'localJDK', maven: 'localMaven') {
			sh 'mvn compile'
			} 
			}

		}
		
	}
}
