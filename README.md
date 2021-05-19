# Application Scaffolding 
This is a basic scaffolding for a Angular/Laravel app.

# Installation Requirements
In order to use this application scaffolding first ensure that the following software is installed :
    1. Node.js : https://nodejs.org/en/download/
    2. Git : https://git-scm.com/downloads (install git bash as well if your using a windows operating systems)
    3. Virtualbox : https://www.virtualbox.org/wiki/Downloads
    4. Vagrant : https://www.vagrantup.com/downloads
    5. Generate a ssh key 

# Setup Instruction
Please Note: Run all instructions in git bash if your using a windows operating systems
1. Install Laravel Homestead
    Step 1: Open git bash then clone the Homestead repository by running the below command :
            
            git clone https://github.com/laravel/homestead.git ~/Homestead

    Step 2: Change directory to Homestead by running the below command :
            
            cd Homestead

    Step 3: Select the current homestead version by running the below command :
            
            git checkout release

    Step 4: Execute the bash init.bat command running the below command :
            
            init.bat
    
    Step 5: Install the nfs vagrant plugin by running the below command :
           
            vagrant plugin install vagrant-winnfsd

    Step 6: In the Homestead directory open the Homestead.yaml file in a text editor e.g vs code / notepad .

    Step 7: In the folders section of the Homestead.yaml document update it with the following settings as shown below (only choose one section for your system):
        
        #Please Note settings are for Windows:
        folders:
            - map: C:\Users\{Enter your Windows Folder name}\app\backend
            to: /home/vagrant/app
            type: "nfs"
                
        #Please Note settings are for linux        
        folders:
            - map: ~/app/backend
                to: /home/vagrant/app
                type: "nfs"

    Step 8: In the site section of the Homestead.yaml document update the following settings as shown below:
        
        sites:
            - map: backend.app
              to: /home/vagrant/app/public

    Step 9: In the features section of the Homestead.yaml document update the following settings as shown below then save all changes to Homestead.yaml:

        features:
            - mysql: true
            - docker: true
            - mariadb: false
            - postgresql: false
            - ohmyzsh: false
            - webdriver: false

    Step 10: In the git bash console type the following commands to download this Application scaffolding :
        
        cd ~
        git clone git@github.com:kabeloatpraesignis/app.git
    
For more installation instructions on how to setup homestead visit https://laravel.com/docs/8.x/homestead


# How to run application
    Step 1: Open the git bash console and navigate to the Homestead folder:

        cd ~/Homestead

    Step 2: then run the vagrant up command as shown below (this command will take a while on the first time you run it) :
        
        vagrant up

    Step 3: In git bash navigate to the frontend folder as shown below:

        cd ~/app/frontend

    Step 4: Execute the below command then paste "localhost:4200" in your browser to see your application 

        npm start
