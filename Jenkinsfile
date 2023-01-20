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
		 //def url = "http://localhost:8080/job/Mutual-Exclusion%20Feature/build?delay=0sec".toURL()
		
		 dir("/home/lakshmi/dell_pods/poky/build/conf")  
		 {
      	           sh '''#!/bin/bash
		 
		      xdg-open http://localhost:8080/job/Mutual-Exclusion%20Feature/build?delay=0sec
		
		 	'''	
		
			
		 }
		}
	    	} 
  }
  }
  }
  
  }
