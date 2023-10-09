<h1> Natas level 0 -> 1 writeup </h1>

# Login
Username: natas1  
Password: g9D9cREhslqBKtcA2uocGHPfMZVzeFK6  
URL:      [http://natas0.natas.labs.overthewire.org](http://natas1.natas.labs.overthewire.org)

# Task
You can find the password for the next level on this page, but rightclicking has been blocked!

# Theory
None

# Solution
1. Browser approach:
  - First, you will see a nearly-blank site when accessing the site given. 
  - As nothing in the site's content, I try to read the source code by right-clicking on the web page:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/543cb49f-7f6f-47b6-ab28-d20cd624dbf0)

  - Unfortunately, right - clicking has been blocked, so I think I will use *Ctrl + U* or *F12* to open the source code:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/2a673e34-acf9-4a6e-963d-8340d39ba314)



2. Ubuntu command lines approach:
  * Mini theory:
      - If you want to connect to a website via Linux shell, using *curl* is a good method. *curl* is a command that send a *GET request*
      to a website that requires authentication or not. The username and password sent by this command are not encrypted, so you
      should use it in a safe environment.

  - I use this command to access the site with given username and password:
    *curl --user username:password websiteurl*
      - *--user* is a flag that tell the *curl* command to send username and password to the server for authentication.
      - *websiteurl* is the site you want to access
        
  - This approach is a little bit less complex than browser approach because you just need a command line.

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/329f6207-6fac-4c29-aa7f-f3cf7eea3be6)

- **Password:** h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7
