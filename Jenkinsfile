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
		 return [
			 env.choices:deselected]
			
		 echo "${env.choices}"
		}
	    	} 
  }
  }
  }
  
  }
