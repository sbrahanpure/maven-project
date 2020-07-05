pipeline
{
agent any
	stages
	{
	stage ( 'SCM Integrate' )
		{
		steps { git 'https://github.com/sbrahanpure/maven-project' }

		}
		
		stage ( 'Compile' )
		{
		steps { withMaven(jdk: 'localJDK', maven: 'localMaven') {
			sh 'mvn compile'
			} 
			}

		}
		
		stage ( 'package' )
		{
		steps { withMaven(jdk: 'localJDK', maven: 'localMaven') {
			sh 'mvn package'
			} 
			}

		}
	}
}
