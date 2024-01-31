Peter Wang. CSE 15L. Lab Report 2.
---

On Servers and SSH Keys.

---

Code for ```ChatServer.java```:
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/6f07c722-7c75-4a4f-892a-2d53957d9efb)
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/e5379fd0-b5f2-4a82-b410-c2d2f53403a5)

1st example of using ```add-message```
- Method ```Handler.handlerequest``` is called
- The argument for `handlerequest` is `url` which is of type `URI` from `import java.net.URI`. It's value is `http://localhost:1629/add-message?s=romans&user=paul`. The fields in the class are `message` and `username`. The value of `message` is initialized as the String `""` and the value of `username` is intialized as the String `""`.
- The values of `message` and `username` are updated in the method. The String array `parameters` is initialized with `url.getQuery().split("=")`, which means that `parameters` holds three elements: `s`, `romans&user`, and `paul`. The String array `middle` is initialized with `parameters[1].split("&")`, which means that The variable `message` is updated to hold 
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/6841926e-ff31-493d-9fd1-eb95fbe41ad9)


2nd example of using ```add-message```
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/66047c9f-a04b-4a5b-813e-8008a7e2fbc8)





---

1a.
