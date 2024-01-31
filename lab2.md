Peter Wang. CSE 15L. Lab Report 2.
---

On Servers and SSH Keys.

---
Part 1
Code for ```ChatServer.java```:
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/6f07c722-7c75-4a4f-892a-2d53957d9efb)
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/e5379fd0-b5f2-4a82-b410-c2d2f53403a5)

1st example of using ```add-message```
- Method ```Handler.handlerequest``` is called
- The argument for `Handler.handlerequest` is `url` which is of type `URI` from `import java.net.URI`. It's value is `/add-message?s=romans&user=paul`. The fields in the class are `message`, `username`, and `messages`. The value of `message` is initialized as the String `""` and the value of `username` is intialized as the String `""`. The value of `messages` is initialized as an empty `ArrayList` with type a `<String>`.
- The values of `message`, `username`, and `messages` are updated in the method. The String array `parameters` is initialized with `url.getQuery().split("=")`, which means that `parameters` holds three elements: `s`, `romans&user`, and `paul`. The String array `middle` is initialized with `parameters[1].split("&")`, which means that `middle` holds two elements: `romans` and `user`. The variable `message` is updated to hold the String at index 0 of `middle`, which is `romans`. The variable `username` is updated to hold the String at index 2 of `parameters`, which is `paul`. Finally, the ArrayList `messages` is updated by calling `.add` with `username: + ": " + message`, so now there is one element in `messages` that is `paul: romans`.
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/6841926e-ff31-493d-9fd1-eb95fbe41ad9)


2nd example of using ```add-message```
- Method ```Handler.handlerequest``` is called
- The argument for `Handler.handlerequest` is `url` which is of type `URI` from `import java.net.URI`. It's value is `/add-message?s=justified%20by%20faith%20alone&user=martin%20luther`. The fields in the class are `message`, `username`, and `messages`. The value of `message` is initialized as the String `""` and the value of `username` is intialized as the String `""`. The value of `messages` is initialized as an empty `ArrayList` with type a `<String>`.
- The values of `message`, `username`, and `messages` are updated in the method. The String array `parameters` is initialized with `url.getQuery().split("=")`, which means that `parameters` holds three elements: `s`, `justified by faith alone&user`, and `martin luther`. The String array `middle` is initialized with `parameters[1].split("&")`, which means that `middle` holds two elements: `justified by faith alone` and `user`. The variable `message` is updated to hold the String at index 0 of `middle`, which is `justified by faith alone`. The variable `username` is updated to hold the String at index 2 of `parameters`, which is `martin luther`. Finally, the ArrayList `messages` is updated by calling `.add` with `username: + ": " + message`, so now there is now two elements in `messages`. The first element `paul: romans` was added from the last call of this method, and the second element is added by this call, which is `martin luther: justified by faith alone`.
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/66047c9f-a04b-4a5b-813e-8008a7e2fbc8)
---
Part 2

The absolute path to the private key for my SSH key for logging into `ieng6` is `/c/Users/peter/.ssh/id.rsa`
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/1c289a1f-473a-48a9-8654-5d34eac3093b)


The absolute path to the public key for my SSH key for logging into `ieng6` is `/c/Users/peter/.ssh/id.rsa.pub`
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/8b23e1e0-4faa-4f93-8caa-91534d1527ed)

Here is the terminal interaction when I log into my `ieng6` account without being asked for a password.
![image](https://github.com/petruswagnavian/cse15l-lab-reports/assets/141669683/00cd15ec-6f29-4db7-b64a-f00977fc1070)





---

1a.
