<h1> Natas level 0 writeup </h1>

# Login
Username: natas0  
Password: natas0  
URL:      http://natas0.natas.labs.overthewire.org

# Task
You can find the password for the next level on this page.

# Theory
None

# Solution
1. Browser approach:
  - First, you will see a nearly-blank site when accessing the site given. 
  - As nothing in the site's content, I try to read the source code:
    
  ![387587314_281753518068565_9192887981679137877_n](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/9580e5db-9a7d-4213-a694-eafaa5ecfd5a)

  ![Capture](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/123eb7ee-ca89-44c9-bb16-07693c9f42f6)

2. Ubuntu command lines approach:
  * Mini theory:
      - If you want to connect to a website via Linux shell, using *curl* is a good method. *curl* is a command that send a *GET request*
      to a website that requires authentication or not. The username and password sent by this command are not encrypted, so you
      should use it in a safe environment.

  - I use this command to access the site with given username and password:
    `curl --user username:password websiteurl`
      - `--user` is a flag that tells the *curl* command to send a username and password to the server for authentication.
      - `websiteurl` is the site you want to access
        
    ![Capture](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/8f7f5a6a-e234-45e5-908e-22cf26361f42)
- **Password:** g9D9cREhslqBKtcA2uocGHPfMZVzeFK6
