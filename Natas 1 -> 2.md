<h1> Natas level 1 -> 2 writeup </h1>

# Login
Username: natas2  
Password: h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7  
URL:      http://natas2.natas.labs.overthewire.org

# Task
There is nothing on this page.

# Theory
None

# Solution
1. Browser approach:
  - First, you will see a nearly blank site when accessing the site given. 
  - As there is nothing in the site's content, I try to read the source code by *Ctrl + U*:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/0a68cb8a-e22a-4669-8509-e671036c51a9)

  - As I can see, there is nothing on the source code to read, except line *\<img src="files/pixel.png">*
  - Access to the image source, I found it was just a boring pixel image.
  - But, when I look at the URL bar:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/e1eb3d32-5214-4b4d-8cef-69576b31148b)

  - You can see that, the .png is stored in a directory called "files", which means there will be something in "files".
  - To access the "files" directory, just delete the /pixel.png on the link:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/b50145a8-9a46-4b5f-bfa2-27208958dc1d)

  - Okay, *users.txt* ?? Seems interesting:
  
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/ba5aaedb-e60b-4c57-a663-ac477ed27245)

2. Ubuntu command lines approach:
  - Simply, just use the command `curl` (used at natas 0 -> 1) to access and read the source code of the site:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/c3e28266-8d73-4bc1-aa53-4820b54c53fd)

  - See that, there is a file called */files/pixel.png*. So I should navigate the "files" directory:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/a3952af0-45a5-462d-8cee-bf8a45349087)

  - In HTML, the tag `<a>` combined with the `href` attribute is used to specify the URL of the page the link goes to. It can point to another website, files, or something else [(article)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
  - In this case, it points to a file called "users.txt", so I should read it:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/8216ea15-82e2-42d9-9d25-42c5c6c1a18c)


- **Password:** G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q
