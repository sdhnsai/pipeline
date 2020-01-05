pipeline { 
	agent any
		stages {
			stage('One) {
				steps {
					echo 'Hi, this is sai'
				}
		}
		stage('Two') {
			steps {
				input('do u want to proced?')
			}
		}
		stage('Three') {
			when { 
				not {
					branch "master"
				}
			}
			steps {
				echo "hello"
			}
		} 
		stage('Four') {
				parallel {
					stage('unit test') {
							   steps {
								 echo "Running the unit test."
							   }
					}
					stage('integration test') {
							   agent {
								 docker {
									 reuseNode false
									 image 'ubuntu'
								}
							  }
							  steps {
								echo 'runnnig the integration test..'
							  }
					}
				}
		}
		}
		}
		}
