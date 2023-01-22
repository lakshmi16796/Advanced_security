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
	    
		dir("/home/lakshmi/dell_pods/poky/build/conf")  
		  {
      	        	sh '''#!/bin/bash
			input=$(printenv choices)
			echo "your input"
			echo "$input"
			
			#Selecting common features and storing it into Properties file
			n=$(grep -rin "####" local.conf | awk '{print $2 }')
			echo "recognised pattern is"
			#echo $n
			x=$(echo $n | sed 's/ /,/g')
			#echo "x is"
			echo $x
			> Properties
			echo "feature=$x" >> Properties
			
			#Selecting Advanced features and storing it into adv_properties file
			n=$(grep -rin "###" local.conf | awk '{print $2 }')
			echo "recognised pattern is"
			#echo $n
			x=$(echo $n | sed 's/ /,/g')
			#echo "x is"
			echo $x
			> adv_properties
			echo "adv_feature=$x" >> adv_properties
			
			array=()
			IFS='+, ' read -ra array <<< $input
			for i in "${array[@]}"; do
  				echo "$i"
			
			#line=$(sed -n "/$i/p" local.conf | head -1)
        		#echo "$line"
		
			n=$(grep -rin $i local.conf | head -1 | awk '{print $1 }' | cut -d: -f 1)
			echo "Line number is"
			echo "$n"
		
			lines=$(grep -rin $i local.conf | head -1 | awk '{print $1}' | cut -d# -f 4)
			echo "Number of lines to edit is"
			echo "$lines"
		
			#Enabling the mentioned feature for build in local.conf 
			sum=$n
			for (( x=1 ; x<=$lines ; x++ )); 
			do
				echo "iterator is"	
	  			echo "$x"
				sum=$(($sum + 1))
				echo "$sum"
    				sed -i "$sum s/#//" local.conf
		
			done
			done
			
			
					
			'''
		  }
		
		
		} 
  }
  }
  }
  
  }
  
