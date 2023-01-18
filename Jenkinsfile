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
			
			n=$(grep -rin "###" local.conf | awk '{print $2 }')
			echo "recognised pattern is"
			#echo $n
			x=$(echo $n | sed 's/ /,/g')
			#echo "x is"
			echo $x
			> Properties
			echo "feature=$x" >> Properties
			
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
			
			cd /home/lakshmi/dell_pods/poky
			pwd
			source oe-init-build-env
			pwd
			#rm -rf bitbake.lock
			#bitbake -c clean core-image-pods
			bitbake core-image-pods
	
	
			cd /home/lakshmi/dell_pods/poky/build/conf
			pwd
			
			echo "Restroing local.conf"
	
		for i in "${array[@]}"; do
  			echo "$i"
		
			#line1=$(sed -n "/$i/p" local.conf | head -1)
        		#echo "$line1"
		
			n1=$(grep -rin $i local.conf | head -1 | awk '{print $1 }' | cut -d: -f 1)
			echo "Line number is"
			echo "$n1"
			lines1=$(grep -rin $i local.conf | head -1 | awk '{print $1}' | cut -d# -f 4)
			echo "Number of lines to edit is"
			echo "$lines1"
		
			#Disabling the mentioned feature for build in local.conf 
			sum1=$n1
			for (( x=1 ; x<=$lines1 ; x++ )); 
			do
				echo "iterator is"	
	  			echo "$x"
				sum1=$(($sum1 + 1))
				echo "$sum1"
    				sed -i "$sum1 s/^/#/" local.conf
			done
		done
					
			'''
		  }
		
		
		} 
  }
  }
  }
  
  }
