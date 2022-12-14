# Code-Refactor
## Description:
The purpose of this project is to refactor the existing website by adding semantic HTML elements to meet accessibility standards and to consolidate and organize the css selector/properties.
## Technology Used 

| Technology Used         | Resource URL           | 
| ------------- |:-------------:| 
| HTML    | [https://developer.mozilla.org/en-US/docs/Web/HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) | 
| CSS     | [https://developer.mozilla.org/en-US/docs/Web/CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)      |   
| Git | [https://git-scm.com/](https://git-scm.com/)     |    
## Code snippets:
```html
<div class="header">
        <h1>Hori<span class="seo">seo</span>n</h1>
        <div>
            <ul>
                <li>
                    <a href="#search-engine-optimization">Search Engine Optimization</a>
                </li>
                <li>
                    <a href="#online-reputation-management">Online Reputation Management</a>
                </li>
                <li>
                    <a href="#social-media-marketing">Social Media Marketing</a>
                </li>
            </ul>
        </div>
    </div>
```

```html
<header>
        <h1>Hori<span class="seo">seo</span>n</h1>
        <nav>
            <ul>
                <li>
                    <a href="#search-engine-optimization">Search Engine Optimization</a>
                </li>
                <li>
                    <a href="#online-reputation-management">Online Reputation Management</a>
                </li>
                <li>
                    <a href="#social-media-marketing">Social Media Marketing</a>
                </li>
            </ul>
        </nav>
    </header>

```
Converting the above non-semantic div with the class of 'header' to header(semantic element) and div to nav(semantic) for links to an appropriate (https://www.w3schools.com/html/html5_semantic_elements.asp). 
This change require some additional modification to the CSS selector: 

```css
.header {
    padding: 20px;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    background-color: #2a607c;
    color: #ffffff;
}
.header div {
    padding-top: 15px;
    margin-right: 20px;
    float: right;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    font-size: 20px;
}

/* to all ul tag under nav which is under header */
.header div ul {
    list-style-type: none;
}

/* to all li under ul tag under nav which is under header */
.header div ul li {
    display: inline-block;
    margin-left: 25px;
}
```

No longer targeting the element on the page with the class of 'header' but instead the css selector targeting the 'header' element and div as nav

```css
header {
    padding: 20px;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    background-color: #2a607c;
    color: #ffffff;
}
header nav {
    padding-top: 15px;
    margin-right: 20px;
    float: right;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    font-size: 20px;
}

header nav ul {
    list-style-type: none;
}

header nav ul li {
    display: inline-block;
    margin-left: 25px;
}

```
```html
<section id="search-engine-optimization" class="search-engine-optimization">
                <img src="./assets/images/search-engine-optimization.jpg" class="float-left" alt="a picture depicting the need of Optimization"/>
                <h2>Search Engine Optimization</h2>
                <p>
                    The dominance of mobile internet use means that users are searching for the right business as they travel, shop, or sit on their couch at home. Search Engine Optimization (SEO) allows you to increase your visibility and find the right customers for your business.
                </p>
            </section>
            <section id="online-reputation-management" class="online-reputation-management">
                <img src="./assets/images/online-reputation-management.jpg" class="float-right" alt="picture of an graph representing the reputation of the business"/>
                <h2>Online Reputation Management</h2>
                <p>
                    The web is full of opinions, and some of these can be negative. Social media allows anyone with an internet connection to say whatever they want about your business. Online Reputation Management gives you the control over what potential customers see when they search for your business.
                </p>
            </section>
            <section id="social-media-marketing" class="social-media-marketing">
                <img src="./assets/images/social-media-marketing.jpg" class="float-left" alt="social media handles - like,share,tweet"/>
                <h2>Social Media Marketing</h2>
                <p>
                    Social media continues to have a sizable influence on buying habits. Social media marketing helps you determine which platforms are suited to your brand, using analytics to find the right markets and increase your lead generation.
                </p>
            </section>
```
grouping all class as one class naming content-section
```html
<section id="search-engine-optimization" class="content-section">
                <img src="./assets/images/search-engine-optimization.jpg" class="float-left" alt="a picture depicting the need of Optimization"/>
                <h2>Search Engine Optimization</h2>
                <p>
                    The dominance of mobile internet use means that users are searching for the right business as they travel, shop, or sit on their couch at home. Search Engine Optimization (SEO) allows you to increase your visibility and find the right customers for your business.
                </p>
            </section>
            <section id="online-reputation-management" class="content-section">
                <img src="./assets/images/online-reputation-management.jpg" class="float-right" alt="picture of an graph representing the reputation of the business"/>
                <h2>Online Reputation Management</h2>
                <p>
                    The web is full of opinions, and some of these can be negative. Social media allows anyone with an internet connection to say whatever they want about your business. Online Reputation Management gives you the control over what potential customers see when they search for your business.
                </p>
            </section>
            <section id="social-media-marketing" class="content-section">
                <img src="./assets/images/social-media-marketing.jpg" class="float-left" alt="social media handles - like,share,tweet"/>
                <h2>Social Media Marketing</h2>
                <p>
                    Social media continues to have a sizable influence on buying habits. Social media marketing helps you determine which platforms are suited to your brand, using analytics to find the right markets and increase your lead generation.
                </p>
            </section>
 ```
 
 the correspondig css changes:
 ```css
 .content-section {
    margin-bottom: 20px;
    padding: 50px;
    height: 300px;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    background-color: #0072bb;
    color: #ffffff;
}

.content-section img{
    max-height: 200px;
}

.content-section h2 {
    margin-bottom: 20px;
    font-size: 36px;
}
```
## Outcome
Through this project i learnt the importance of structuring HTML and CSS pages by adding comments and semantic elements to meet accessibility standards which also makes it easier to debug the code when problem arises.
## Links
Github repo: https://github.com/srinithi19/refactor-site             
Application URL : https://srinithi19.github.io/refactor-site/
