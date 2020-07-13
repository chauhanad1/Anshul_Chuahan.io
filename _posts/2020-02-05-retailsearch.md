---
title: " Recommendation System Based Retail Search Application"
date: 2020-02-05
tags: [Machine Learning, Full Stack]
header:
    image: "/images/retailsearch/main_pic.png"
excerpt: "Machine Learning, Bootstrap, Django, Recommendation System "
---

> In the world of online shopping we literally forget local retailers in nearby areas. There are ample of online applications available to shop or buy things. But there are some disadvantages. Some online applications take too long to deliver. Also, buying things like apparels, shoes, furniture cannot ensure customer satisfaction to the fullest. To make customers satisfied and to experience the touch and feel of product it is important to physically see that product. Hence, here comes the role of local retailers. But local retailers lacks in communication with customers. It takes time to find the shop which meets their needs. So, to make it easier for users to reach retailers it is necessary to have an application which allows them to search for local shops and get the product availability in that shop to choose the suitable one.

The overall design of the project is: 
<img src="{{ site.url }}{{ site.baseurl }}/images/retailsearch/architecture.png" alt="architecture">

The Project has 3 modules:

1. **Front End** 
> Front end is created using Bootstrap libraries and java script,Html and CSS. There will be a login page, sign up page and the website. They are designed as follows:

<img src="{{ site.url }}{{ site.baseurl }}/images/retailsearch/login.png" alt="architecture">

<img src="{{ site.url }}{{ site.baseurl }}/images/retailsearch/signup.png" alt="architecture">

<img src="{{ site.url }}{{ site.baseurl }}/images/retailsearch/homepage.png" alt="architecture">

2. **Back End**
> Backend is implemented on Django framework along with libraries like geo Django for the coordinates. The database is a relational database created in PostgreSQL. The get query contains two parameters that is search query string and User's coordinate. This user's coordinate will be used to search the surrounding area within radius of 7 km to provide the list of local shops with the desired product.

3. **Recommendation System**
> *Content Based Recommendation System* are used to recommend the items on the basis of contents. For example the Item which is rated highest by users will be shown to new users. Since this does not provide personalize taste, *Collaborative filtering methods* are also used. Since the size of sparse matrix are huge, Matrix factorization is also used to reduce processing time.