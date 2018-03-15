node{
        stage('Test') {        
			withAWS(credentials:'AWS', region:"us-east-2") { 
                
				def outputs = cfnUpdate(stack:'my-stack', tags:["Name=MyInstance"], url:'https://s3.us-east-2.amazonaws.com/wk-config-global-2/integrate-with-jenkins/wk-iam-global-pipeline.yaml')
		}
            
        }
}