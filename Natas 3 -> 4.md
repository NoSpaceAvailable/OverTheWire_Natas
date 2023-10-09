<h1> Natas level 3 -> 4 writeup </h1>

# Login
Username: natas4  
Password: tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm  
URL:      http://natas4.natas.labs.overthewire.org

# Task
Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"

# Theory  
-*The **Referer** HTTP request header contains the absolute or partial address from which a resource has been requested. The Referer header allows a server to identify referring pages that people are visiting from or where requested resources are being used. This data can be used for analytics, logging, optimized caching, and more.* 
- For example, if you are on website1 and click the link to website2 (the link is on website1), a Referer header will be sent to website2's server. Therefore, website2 will know that you come there via website1. [(Article)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer)
- You should know a little about how HTTP/HTTPS headers works. [(Article)](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
# Solution
1. Tools approach:
  - When accessing natas4 site, you will see a message: "Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/""
  - That means, natas4 only accept users who come from natas5 site, but if you want to access natas5, you have to solve natas4.
  - If you read the article attached on *Theory* above, you will know that we just have to put a Referer header with the request sent to natas4 server. The header will contain natas5 site.
  - I use Microsoft Edge, so I can't edit headers of a site (Edge blocked this). I use a tool called "Burp Suite" to handle requests.
  - I recommend to use Burp Suite, because it's a standard tool for websec, and also very useful.
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/6baa437a-d2e6-4dca-8f9b-78f8f869f87d)

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/41f20cb3-8087-4752-9825-a4f4974b31b7)

  - Input username and password as normal.
  - You will see this:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/c09206ad-7377-45b8-9768-bff5d30e3f87)

  - Right-click on it and choose "send to repeater"
  - Then navigate to the repeater:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/79ce11cd-64af-4fa3-ae47-8715d4e455ec)

  - Add Referer header with natas5 link as below, then send:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/41b82062-f83f-44c7-981f-1e31ec7f356b)

  - The password will be in the response field:

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/e1afa211-a88a-4267-bb46-6e5c9865928a)

  - You have to know the basics of Burp Suite. [See this link](https://portswigger.net/burp/documentation/desktop/getting-started)

2. Python approach:
  - Okay, cyber security still has to code. Recommend you guys to use this approach, too.
  - To send a request to a web server, you have to use a Python module called "requests". [How to install](https://pypi.org/project/requests/)
  - A request has to have headers, of course. If you don't know what headers you should send, I'll show:

  ![Capture](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/5c9ea681-cfc0-4ee1-9992-c61551a43969)

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/bb0ab815-4413-4a8c-a9ce-971a4b506543)

  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/78b2c81c-7b98-45dd-abc3-ac789359c963)

  - Copy all headers and open your code IDE (I use VSCode). Don't forget to add *Referer* header! This is a simple request implementation:
    
  ![image](https://github.com/NoSpaceAvailable/OverTheWire_Natas/assets/143888307/ed90097e-dcab-49ad-99a2-2d8ad94fdbca)

  - Don't know why can I write this code? [This will help](https://reqbin.com/code/python/ixa9gi7o/python-http-request-example#:~:text=To%20send%20an%20HTTP%20request,set%20rate%20limits%20and%20timeouts.)

- **Password:** Z0NsrtIkJoKALBCLi5eqFfcRN82Au2oD
