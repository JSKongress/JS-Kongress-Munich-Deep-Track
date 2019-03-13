# JS Doc and others

by [Philip  // @cowglow](https://twitter.com/cowglow/)

The goal was to interact developer who have used JS Doc or other documentation tools 

## Discussion

**Why use JS Doc?**
- To not be `that.guy`
- Enable me and other developers to contextualize code
- To generate API documentation for delivery of software

**Example of usage**
- Annotations on JavaScript Class
    ```
    /**
     * Method name
     * @param {string} $var1 - Variable one
     * @param {number} $var2 - Variable two
     */
    ClassName.prototype.methodName($var1, $var2) ...
    ```
- Annotations to generate API
  One of the participants shows us how he is using JS Doc to generate documentation for this software written in JAVA
  He included example on his JS Doc blocks. Which was really interesting to see, how JS Doc can still be used for a 
  project that isn't necessarily written in JavaScript.
  
**Take aways**
- It's always better to start with documentation from the start of the project
- JS Doc templates seem to be hard to understand and JS Doc's out of the box template isn't idea for usage
- Additional configuration is needed 