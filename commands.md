# Commands Used – Task 7: Environment Variables & PATH

## 1. Viewing Environment Variables               
- `printenv`                    
Displays all environment variables available in the current shell session.                                   
Used to inspect existing runtime variables such as PATH, HOME, USER, and SHELL.                 
- `env`                        
Prints the list of environment variables and their values.                                   
Commonly used to verify exported variables.                       
- `echo $PATH`              
Displays the current PATH variable.                                  
PATH contains a colon-separated list of directories that the shell searches for executable commands.                            

## 2. Creating Custom Variables                 
- `MY_NAME=Tejashwini`                      
Creates a shell-local variable available only in the current shell.                    
This variable is not accessible to child processes or scripts.                           
- `echo $MY_NAME`                    
Prints the value of the variable to confirm it is set.                        

## 3. Exporting Environment Variables
- `export NAME=TEJU`                 
Creates an environment variable that is inherited by child shells, scripts, and applications.                   
### Verify exported variable                   
- `echo $NAME`                     
Confirms that the variable has been successfully exported.                         

## 4. Testing Variable Scope Using a Script
- `cat test.sh`                             
- `#!/bin/bash                       
   echo "MY_NAME=$MY_NAME"                                   
   echo "Name is : $NAME"`                                  
This script prints both shell-local and exported variables to demonstrate variable scope.               
### Execute script                     
- `./test.sh`              
Runs the script in a child shell.              
Shell-local variables are not visible, while exported variables are accessible.                      

## 5. Modifying PATH Variable (Temporary)
### Add directory to PATH                 
- `export PATH=$PATH:/home/user/scripts/test.sh`                
Appends a custom directory to the existing PATH variable.               
This allows scripts in the directory to be executed without specifying the full path.             
### Verify PATH update                    
- `echo $PATH`             
Confirms that the new directory has been added to PATH.             

## 6. Making Environment Variables Persistent
### Edit .bashrc                
- `vi ~/.bashrc`             
Opens the Bash runtime configuration file used to load variables at shell startup.               
### Add persistent variables                
- `export MY_NAME=Tejashwini              
   export NAME=TEJU          
  export PATH=$PATH:/home/user/scripts/test.sh`              
Ensures variables are automatically set for every new shell session.                  
### Reloading Configuration                  
- `source ~/.bashrc`                       
Reloads the .bashrc file without requiring logout or reboot.                       
Makes newly added variables available immediately.                 

## 7. Testing Persistence Across Sessions
### Verify variables                 
- `echo $MY_NAME                   
   echo $NAME`                  
Confirms that variables are loaded successfully.                
### Open new shell            
Check variables in new shell                 
- `echo $NAME`                  
Verifies that exported variables persist across new shell sessions.                            
- `exit`             

## 9. Debugging PATH-Related Issues
- `which ls`            
Displays the full path of the command if it exists in PATH.                     
- `type test.sh`            
Shows how the shell resolves a command.                 
- `ls /home/ubuntu/scripts/test.sh`                 
Ensures the script exists in the directory added to PATH.                 
- `ls -l test.sh`             
Verifies whether the script has execute permissions.                 
- `chmod +x test.sh`                
Makes the script executable.                 
- `/home/user/scripts/test.sh`               
Used to isolate PATH-related issues by running the script directly.                

## Conclusion
These commands demonstrate how environment variables and PATH are configured, tested, persisted, and debugged in Linux systems—core skills required for DevOps and system administration roles.
