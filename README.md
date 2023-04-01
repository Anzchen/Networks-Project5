# Networks-Project5

This is the fifth project for Networks & Distributed Systems course. 

The assignment description is below:
This assignment is intended to familiarize you with the HTTP protocol. HTTP is (arguably) the most important application level protocol on the Internet today: the Web runs on HTTP, and increasingly other applications use HTTP as well (including Bittorrent, streaming video, Facebook and Twitter’s social APIs, etc.).

Your goal in this assignment is to implement a web crawler that gathers data from a fake social networking website that we have set up for you. There are several educational goals of this project:

- To expose you to the HTTP protocol, which underlies a large (and growing) number of applications and services today.
- To let you see how web pages are structured using HTML.
- To give you experience implementing a client for a well-specified network protocol.
- To have you understand how web crawlers work, and how they are used to implement popular web services today.

## High-Level Approach

The protocol is implemented in Python. First we used `socket` and `ssl` to create a connection to the server and send and receive data from it. Then we used `HTMLParser` in order to read data from the HTML pages through creating the LinkParser class, which took out the `href` attribute. Then we ran a loop, which starts from the first page and searches for all links and any secret flags on the page and adds them to the unvisited array, and adds the current page to the visited set. It performs those same actions for every page in its unvisited array, crawling all links from the first page until all 5 secret flags are found. Each page may return different HTTP responses which cause differing responses.

## Challenges Faced
1. **Learning HTTP**: Using the "HTTP Made Really Easy" tutorial, we were able to understand how to work with HTTP syxtax
2. **Implementing HTMLParser**: Learning how to use HTMLParser and creating the LinkParser and handling the start tag to grab the `href` attribute
3. **Gathering the flags**: We found it difficult to debug the code and find where the problem was that made it not find the flags correctly each time, but in the end found we used the wrong syntax for some methods.

## Features

1. **Error Handling**: The application replies  to various HTTP status codes. For instance, the application will go on to the next Address if a page returns a "404 Not Found" message. The application will retry the request by adding the URL back to the list of pages to visit if a page returns a "503 Service Unavailable" error.
2. **Throttling**: The application manages the pages to be visited using a straightforward list-based system. Any new links discovered on a page are appended to the end of the list once the page has been visited, which also removes the page from the list of pages to visit. By doing this, it is made sure that pages are visited in the order they are found.
3. **Selective Repeat**: The selective repeat mechanism in the receiver ensures that only the missing packets are retransmitted, improving overall transmission efficiency.

## Testing
We tested and debugged our code by constantly printing the received data and checking what issues we were getting. We also submitted to GradeScope over and over again to see which errors were getting returned. We also tested our loop through creating a separate program, which used the same functionality and ensured it worked on a smaller dataset, then implemented it into our crawler.
