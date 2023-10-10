<h1> Natas level 4 -> 5 writeup </h1>

# Login
Username: natas5  
Password: fOIvE0MDtPTgRhqmmvvAOt2EfXR6uQgR  
URL:      http://natas5.natas.labs.overthewire.org

# Task
Access disallowed. You are not logged in

# Theory
- You need to know how a site checks whether a user is logged in. There is a thing called "cookies authentication". For easy, when you log in to a site, if you submit the correct username and password, an authentication cookie is set, and it will contain a value to describe that you are the account owner. Otherwise, the authentication cookie is set to a value that describes you are not logged in.
- For more information, [see this](https://swagger.io/docs/specification/authentication/cookie-authentication/).

# Solution
1. Browser approach:
  - When accessing the site, you see a message: "Access disallowed. You are not logged in"
  - Then we should check the network (by F12), at the headers path:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/30652786-627a-459d-b779-43706df9b235)
  
  - See something? There is a header called "Set-Cookies", and it has the value "loggedin=0". Okay, when you read this, you certainly know how to pass this level.
  - I use an extension tool called "EditThisCookies" to edit that header since I don't know how to edit headers on Edge:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/ccb5cf66-dde5-4479-a81f-e7ec3fac8f28)

  - Edit it to 1, and see the result:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/abfaa2f4-ea8a-4e3b-b383-0ed303ae1550)

2. Burp Suite approach:
  - If you read my Natas 3 -> 4 writeup, you certainly know how to use basic Burp Suite. This is how I edit the Set-Cookies header with Burp:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/56e38f27-3d21-4f2a-8307-e8803752d1d0)

  - Then send it to the repeater and hit send. See our result:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/9ea1c723-2d5a-4791-a037-f37c6596c323)

- **Password:** fOIvE0MDtPTgRhqmmvvAOt2EfXR6uQgR
