# Cloud-based GIS: Using REST-based APIs
## Overview

In this tutorial we explore the application of web services to spatial analysis. It’s an exciting and rapidly evolving field: what’s “cutting edge” this year is likely to be old news the next. However, getting in on this technology at an early stage should provide you with a more robust understanding of how it works and thus how you can utilize its power most effectively. At this stage in the development of web services and cloud-based GIS, however, you’ll need to be prepared for bugs and limited documentation. It’s all part of the excitement of being at the forefront of technology.

Here, we begin simply, looking at web services from within web browsers. From there we explore how these services can be controlled via scripts (e.g. Python). Then we examine more advanced interfaces to web services, i.e. via APIs and applications that are integrated with web services (e.g. ArcGIS.com and Desktop ArcGIS).

## Lesson Objectives

* Understand what REST is, in the context of using cloud-based resources
* Identify and implement APIs to fetch data and execute analyses
* Master the use of the Python `requests` library to form and send requests to APIs and handle their responses

---

## What is REST

**REST** (**Re**presentational State **T**ransfer) is a set of principles that govern the design of web services, including APIs (Application Programming Interfaces). RESTful APIs provide a way for two software applications to communicate with each other over the internet.

At its core, REST is a way to structure communication between a client (such as a web browser or mobile app) and a server (such as a web application or database). The principles of REST define a standard way of accessing and manipulating resources (such as data or files) over the internet using HTTP (Hypertext Transfer Protocol).

RESTful APIs typically use HTTP methods (such as GET, POST, PUT, and DELETE) to perform actions on resources. For example, a client can use an HTTP GET request to retrieve information about a resource, such as a user account or a product listing. A client can use an HTTP POST request to create a new resource, such as a new user account or a new product listing.

RESTful APIs also use URLs (Uniform Resource Locators) to identify resources. For example, a URL might be used to identify a specific product listing, such as https://example.com/products/12345. This URL could be used with an HTTP GET request to retrieve information about the product, or with an HTTP PUT request to update the product information.

Overall, RESTful APIs provide a standard way for software applications to communicate with each other over the internet, making it easier for developers to build software that can interact with other systems and services. It is a simple, yet powerful means for expanding spatial analysis, among other tasks, beyond the desktop. 

### REST: An Example

Each time you do something as familiar as a Google search, you are using REST. Give it a try: 

* **Navigate to <https://www.google.com> and search search for "Duke University".**  
  The results are not surprising, but if you look at the web address (i.e. the URL) for the search results page, you'll see your search term (among other things) in it, likely followed by a `q=`. *This URL is a REST-based request!*
* **Copy, paste, and enter the following URL into your browser:**  
  [https://www.google.com/search?q=Nicholas School of the Environment](https://www.google.com/search?q=Nicholas School of the Environment)  
  Here, instead of using Google's familiar search page to enter a search term, we performed the search by issuing the REST based request directly, as a URL. 
* **Try modifying the URL to search for something else**...

So we see that a Google Search acts like REST API where the phrase following the `q=` is the search parameter. 

> **The structure of the Google Search API:**
>
> | URL component                          | Purpose                                                      |
> | -------------------------------------- | ------------------------------------------------------------ |
> | `https://www.google.com`               | The address to where the request should be sent. <br />(This can also include sub folders...) |
> | `search`                               | The request function.                                        |
> | `q=Nicholas School of the Environment` | A parameter of the request function and its value.           |

---

## Geospatial APIs

A Geospatial API is any API that includes location in the request or that returns spatial data. 

