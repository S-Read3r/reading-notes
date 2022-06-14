# Understanding Local storage

the past a, present and future of local storage for web appliations. This is an important concept to grasp when diving deep into the understanding of tech. 

### Persitent Local Storage

this is one of the areas where native client applications have held an advantage over we applications. For native applications the operating system typically provides an abstration ;ayer for storing and retrieving applications, the operating system typically provides and abstraction layer for storing and retrieving application-specific data like preferences or runtime state. These values may be stored in the registry, INI files, XML files , or some other place according to platform convention. If your native client application needs local storage beyend key/value pairs, you can embed your own database, invent your own file format, or any number of other solutions. 

Cookies, were invented early in the web's history, and indeed they can be used for persistent local storage of small amounts of data. But they have three potentially dealbreaking downsides:

* Cookies are included with every HTTP request, thereby slowing down your web application by needlessly transmitting the same data over and over.
* Cookiesare inclueded with every HTTP request, thereby sending data unencrpted over the internet (unless your entire web applications is served over SSL).
* Cookies arelimited to about 4 KB of data - enough to slow down your aplication, but not enough to be terrible useful.

What we really needed in local storage is 
1. a lot of storage space of course
2. on the client 
3. that persists beyond a page refresh... Meaning that storage which won't be affected by a page being refreshed
4. and ISN'T transmitted to the server

It is important to note that before HTML5, a;; attempts to achieve this were ultimatedly unsatisfactory in different ways.

### A brief history on local storage before HTML%

In the time before other web browser, Microsoft sort to win the browser war by implementing something called **userData** which allows web pages to store up to 64 KB of data per domain, in a hierarchical XML-based structure. There was an exception to this rule for trusted domains such as **intranet sites** which can store upto 10 times that amount. Then adobe introduced a frature in Flash 6 that gained the unfortunated and misleading name of 'Flash cookies'. Within the the Flash environment, the feature is properly known as LOcal Shared Objects. **Briefly**, it allows Flash objects ro store up to 100 KB of data per domain. Brad Neuberg develloped an early prototype of a Flash-toJavaScript bridge called AMSSS(AJAX MASSIVE STORAGE STYSTEM), but it was limited by some of Flash's design quirks.Find out more on [This article](http://diveinto.html5doctor.com/storage.html)

### Introduction to HTML5 storage

HTML5 Storage or Web Storage or Local Storage or DOM Storage