pipeline
{
	agent any
	stages
	{
		stage("Create Directory")
		{
			sh 'mkdir MyFolder'
			echo "Folder Has Been Created"
		}
		
		stage("Create File")
		{
			script
			{
				steps
				{
					dir("MyFolder")
					{
						sh 'touch MyFile.txt'
						echo "File Has Been Created"
					}
				}
			}
		}
		
		stage("Write File")
		{
			script
			{
				steps
				{
					dir("MyFolder")
					{
						sh 'echo "Hello From Git" > MyFile.txt'
						echo "File Has Been Writted"
					}
				}
			}
		}

	}
}
