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
		
		
		
		stage ( 'Test' )
		{
		steps { withMaven(jdk: 'localJDK', maven: 'localMaven') {
			sh 'mvn test'
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
		
		stage ( 'Deploy War file' )
		{
		steps {
		sshagent(['552955f2-8eed-4d81-b690-498f642068d2']) {
			sh 'scp -o StrictHostKeyChecking=no */target/webapp.war ec2-user@172.31.17.72:/var/lib/tomcat/webapps '
			
			}
			}

		}

}
	}
}
