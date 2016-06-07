# Virtual Environment

This repo contains a virtual box that you can download, and start from the command line. When you start it up, it will have everything you need to start developing the backend of the UPOD.

## Advantages:

* Everything is self-contained within virtual machine - no need to downlod anything else
* Set-up is done for you - no need to install Ruby, Rails, MySQL
* Everyone who uses this environment will be working with the exact same versioning

## How it works?

1. Download [Vagrant](https://www.vagrantup.com/downloads.html) to install everything required to get the virtual machine up and running.
2. Download the `package.box` from [here](https://mega.nz/#!KsM2AD6a!Lud-Smyh4SQXwqySKAC29WWuct6uVODBhAeeuG4ZXbM). This was originally on Github but we exceeded the data cap in the first hour of `package.box` being hosted here.
3. Start the vagrant box - on Windows, you'll need to go to the command prompt and then run the following commands. Linux and Mac users will need to Terminal.
        
        # `YOUR_PROJECT_DIRECTORY` must have the `package.box` in it.

        cd `YOUR_PROJECT_DIRECTORY`
            
        vagrant box add upod package.box
    
        vagrant init upod
    
        vagrant up
        
        vagrant ssh

4. Configure Github to work with your account.
    
        git config --global user.name "YOUR NAME"
    
        git config --global user.email "YOUR@EMAIL.com"
    
        ssh-keygen -t rsa -b 4096 -C "YOUR@EMAIL.com"
  
  The next step is to take the newly generated SSH key and add it to your Github account. You want to copy and paste the output of the following command and paste it [here](https://github.com/settings/keys).
  
      cat ~/.ssh/id_rsa.pub
  
  Once you've done this, you can check and see if it worked:
  
      ssh -T git@github.com
  
  You should get a message like this:
  
      Hi mikeroher! You've successfully authenticated, but GitHub does not provide shell access.
    
5. Change your directory (with the `cd` command) to /vagrant/UPOD/upod
