<h1> Natas level 2 -> 3 writeup </h1>

# Login
Username: natas3  
Password: G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q    
URL:      http://natas3.natas.labs.overthewire.org

# Task
You can find the password for the next level on this page.

# Theory
- What is a *robots.txt* file?
    - The *robots.txt* file is a special file a website may have. It is used to tell the search engine not to include site(s) in the search results. [(See more)](https://developers.google.com/search/docs/crawling-indexing/robots/intro#:~:text=A%20robots.txt%20file%20tells,or%20password%2Dprotect%20the%20page.)

# Solution
1. Browser approach:
  - First, you will see a nearly blank site when accessing the site given. 
  - As nothing in the site's content, I try to read the source code by `Ctrl + U`:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/ec89df39-7a5b-4d10-889c-33d804ad3688)

  - The red-underlined part is a hint: What prevents Google search from finding a site? It's time to check the robots.txt file:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/ed8070c0-ddf8-4aac-9380-1d0b575cf93a)

  - Okay, there is a hidden file called "s3cr3t" on the web server. Accessing this site may give us something:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/40ad70b7-bf48-4f7a-afaa-c390b077eddf)

  - The task is much easier now:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/eefbdc16-64f3-4e4b-a990-0c8f48f46785)

2. Ubuntu command lines approach:
   
  - **Command**: `curl`   
  - Simply use the command `curl` as the previous challenge.

  - First, read the source code of the site and we'll see a hint:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/b93d32ba-5dd5-4ab5-859b-6773e1de9f94)

  - As theory (mentioned above), I should read the "robots.txt" file to check the hidden files:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/c4c33c3b-1e46-4ee4-a0a8-d583c452b7db)

  - There is a hidden "s3cr3t" file there. Let's check it:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/58273b90-a5d1-41ef-a8ad-85cdfb38ad35)

  - It's here, the "users.txt"! Our last task is very simple:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/496ae589-2bfb-4dbd-a9da-63935229977e)

  - Note:
      - If you use the `curl` command but receive something like this:
        
      ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/e87b5a12-ee1e-448c-90a2-1f553c6c23ee)

      Please remember:
        - If the target URL leads to a directory, the URL has to have a slash symbol '/' at last. Example:
        ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/ed6345ad-829e-4436-a926-872205552683)
        - If the target URL leads to a file, the URL must not contain a slash symbol '/' at last. Example:
        ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/6e8142d9-d996-4a7a-a731-e3582bd4de2d)
    
- **Password:** tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm
