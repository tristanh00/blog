# PHP Basics: Everything about the $_SERVER variable

The `$_SERVER` variable is a superglobal array in PHP that contains information about the server and the request environment. It is an associative array that provides access to various server and execution environment information, such as headers, paths, and script locations.

Some of the most commonly used elements of the `$_SERVER` array include:

`$_SERVER['HTTP_HOST']`: Contains the hostname of the server.
`$_SERVER['HTTP_USER_AGENT']`: Contains the user agent string of the client.
`$_SERVER['REMOTE_ADDR']`: Contains the IP address of the client.
`$_SERVER['REQUEST_URI']`: Contains the URI of the current page.
`$_SERVER['SCRIPT_NAME']`: Contains the path of the current script.
`$_SERVER['REQUEST_METHOD']`: Contains the request method (e.g. `"GET"` or `"POST"`).
`$_SERVER['SERVER_NAME']`: Contains the name of the server.
`$_SERVER['SERVER_PROTOCOL']`: Contains the server protocol (e.g. `"HTTP/1.1"`).
`$_SERVER['SERVER_SOFTWARE']`: Contains the server software and version.
`$_SERVER['PHP_SELF']: Contains the filename of the currently executing script.
`$_SERVER['QUERY_STRING']: Contains the query string from the URL.
`$_SERVER['DOCUMENT_ROOT']: Contains the document root directory for the server.
`$_SERVER['HTTP_ACCEPT']: Contains the Accept header from the request.
`$_SERVER['HTTP_ACCEPT_LANGUAGE']: Contains the Accept-Language header from the request.
`$_SERVER['HTTP_ACCEPT_ENCODING']: Contains the Accept-Encoding header from the request.
`$_SERVER['HTTP_CONNECTION']: Contains the Connection header from the request.
`$_SERVER['CONTENT_TYPE']: Contains the Content-Type header from the request.

These are just a few examples of the information that is available in the `$_SERVER` array. There are many other elements that can be accessed depending on the server and execution environment.

Keep in mind that not all of these keys will be available in every server and execution environment. Some keys may be missing or have different names depending on the server configuration and the information that is available.

Overall, the  `$_SERVER` array is a rich source of information about the server and the current request environment, and provides many useful pieces of data that can be accessed in your PHP scripts.



