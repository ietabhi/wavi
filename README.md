##WAVI Web Application Viewer (Node.js)

Generate a class diagram graph for node.js web application inspired by the Web Application Extension (WAE) for UML.
It is also possible to generate a json report listing files and their relations with metrics.

WAVI is intended for developers who wish to document their web application or as a reverse engineering tool to recover 
the structure of a web application.


## Dependency
```
Require Graphviz installed and PATH variable for Graphviz in your environment variable.

## Installation

    $ npm install wavi -g

```

##Usage (CLI): 

It is strongly advised to use svg format for very large website because jpg/png/pdf are limited in width and height and will most likly not work
or use ratio and the quality will be bad.

wavi --format path/to/website path/to/result/file.type


```
wavi --svg website/example result/example.svg

wavi --jpg website/example result/example.jpg

wavi --png website/example result/example.png

wavi --pdf website/example result/example.pdf

wavi --dot website/example result/example.dot

wavi --svg website/example result/example.svg --includenodemodules

```

##Usage: 

wavi.generateGraph("format","website/example","result/file.type",includenodemodules ...

```
var wavi = require("wavi");

wavi.generateGraph("svg","website/example","result/example2.svg",false,function(err){

});
```

##Parameter

--includenodemodules : include node_modules folder, use this parameter to include relations of "node_modules" folder.


##Example:

![Example](/example/result/example.png?raw=true "Example")

run example/example.cmd in node console or node example


##TROUBLESHOOTING

-If you get a RangeError 
```
RangeError: Maximum call stack size exceeded
```
This means that the website is too big to generate a diagram. You can divide the diagram by pointing subfolders instead of pointing to the whole web application.
"node_modules" often contain too much information for wavi, it is a good idea not to include this folder by not using 
--includenodemodules parameter.


-If your web application is too large and your image is empty or the quality of the image is bad, this means that there is
not sufficent space to draw the diagram. Try using "svg" format.

-Do not run wavi in the root of your web application like:

wavi --pdf . result/example.pdf

This does not work yet. Instead run wavi from a parent folder like in the example.


##Contributions

This is a big project to help developers generate quality class diagram. WAVI is in early development and all contributions are welcomed.
For more info on the project contact me at jugle66@hotmail.com


## License

The MIT License (MIT)
Copyright (c) 2014 Bakunin95
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
