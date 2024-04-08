node {
    stage('SCM') {
	echo 'Gathering code from version control' 
	echo 'Test'
	git branch: '${branch}', url: 'https://github.com/SuggyGH/RichTest.git'
    }
    stage('Build') {
	try {
        	echo 'Building....'
		withDotNet(sdk: "sdk6"){
	    		sh 'dotnet build ConsoleApp1'
	    		echo 'Build new feature'
			releasenotes(changes: "true")
		}
	}
	finally{
		//cleanup
	}
    }
    stage('Test') {
        echo 'Testing....'
    }
    stage('Deploy') {
        echo 'Deploying....'
    }
}
