The Location object represents the current location (URL) of a document. You can access the Location object by referencing the location property of the window or document object.

Both window.location and document.location link to the same Location object.

__JavaScript Location properties__

Suppose that the current URL is:

```JavaScript
http://localhost:8080/js/index.html?type=listing&page=2#title

```

__Location.href__

The location.href is a string that contains the entire URL.

```JavaScript
"http://localhost:8080/js/index.html?type=listing&page=2#title"

```
__Location.protocol__

The location.protocol represents the protocol scheme of the URL including the final colon (:).

```JavaScript
'http:'
```

__Location.host__

The location.host represents the hostname:

```JavaScript
"localhost:8080"
```

__Location.port__

The location.port represents the port number of the URL.

```JavaScript
"8080"
```

__Location.pathname__

The location.pathname contains an initial '/' followed by the path of the URL.

```JavaScript
"/js/index.html"
```

__Location.search__

The location.search is a string that represents the query string of the URL:

```JavaScript
"?type=listing&page=2"
```

__Location.hash__

The location.hash returns a string that contains a ‘#’ followed by the fragment identifier of the URL.

```JavaScript
"#title"
```
__Location.origin__

The location.origin is a string that contains the canonical form of the origin of the specific location.

```JavaScript
"http://localhost:8080"
```

__Location.username__

The location.username is a string that contains the username before the domain name.

__Location.password__

The location.password is a string that represents the password specified before the domain name.

__Manipulating the location__

The Location object has a number of useful methods: assign(), reload(), and replace().

__assign()__

The assign() method accepts an URL, navigate to the URL immediately, and make an entry in the browser’s history stack.

```JavaScript
location.assign('https://www.google.com');

```

When the window.location or location.href is set to a URL, the assign() method is called implicitly:

```JavaScript
window.location = 'https://www.google.com';
location.href = 'https://www.google.com';
```

If you change hostname, pathname, or port property, the page reloads with the new value. Note that changing hash property doesn’t reload the page but does record a new entry in the browser’s history stack.

When a new entry is created in the browser’s history stack, you can click the back button of the browser to navigate to the previous page.

__replace()__

The replace() method is similar to the assign() method except it doesn’t create a new entry in the browser’s history stack. Therefore, you cannot click the back button to go to the previous page.

The following code uses the replace() method to navigate to the URL https://www.google.com after 3 seconds:

```JavaScript
setTimeout(() => {
    location.replace('https://www.javascripttutorial.net');
}, 3000);
```

__reload()__

The reload() method reloads the currently displayed page. When you call the reload() method with no argument, the browser will reload the page in the most efficient way e.g., it loads the page resources from the browser’s cache if they haven’t changed since the last request.

```JavaScript
reload();
```

To force a reload from the server, you pass true to the reload() method:

```JavaScript
reload(true)
```

Note that the code after the reload() may or may not execute, depending on many factors like network latency and system resources. Therefore, it is a good practice to place the reload()  as the last line in the code.

__Redirect to a new URL__

To redirect web browsers to a new URL from the current page to a new one, you use the location object:

```JavaScript
location.href = 'new_url';
```

Assigning a value to the href property of the location object has the same effect as calling the assign() method of the location object:

__Redirect to a relative URL__

The following script redirects to the about.html which is on the same level as the current page.

```JavaScript
location.href = 'about.html';
```

The following script redirects to contact.html page located in the root folder:

```JavaScript
location.href = '/contact.html';
```
__Redirect upon page loading__

If you want to redirect to a new page upon loading, you use the following code:

```JavaScript
window.onload = function() {
    location.href = "https://www.google.com/";
}
```
