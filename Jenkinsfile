pipeline {
  agent any
  stages 
{  
    stage ("User Input Stage")
    {
	    
      steps {	 
	      
	script {
		
                 echo "selected parameter is"	
		 if(env.choices == "Docker")
		{
			
	         echo "${env.choices}"
		 echo "This is Dockers"
		 env.choices:deselected
			
		 echo "selected parameter is"	
		 echo "${env.choices}"
		}
	    	} 
  }
  }
  }
  
  }
