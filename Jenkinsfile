pipeline {
  agent any
  stages 
{  
    stage ("User Input Stage")
    {
	    
      steps {	 
	      
	script {
		
                 echo "selected parameter is"
		 echo "${env.choices}"
		 def url = "http://localhost:8080/job/Mutual-Exclusion%20Feature/build?delay=0sec".toURL()
		 if(env.choices == "Docker,QT")
		{
		 echo "Selected parameter is" 	
	         echo "${env.choices}"
		 echo "$env.BUILD_URL"
		
		
			
		
		}
	    	} 
  }
  }
  }
  
  }
