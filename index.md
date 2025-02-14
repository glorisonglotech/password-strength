# GLOTECH TUTORIALS

## Description 
This HTML document is a simple web page that includes a password input field and a script to evaluate the strength of the entered password. Here's a detailed explanation of the code:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>glotech-tutorials</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <div class="input-box">
            <input type="password" placeholder="password" id="password">
            <img src="image/right-arrow.png" alt="">
        </div>
        <p id="message">Your password strength is <span id="strength"></span></p>
    </div>
    <script>
        let password = document.getElementById('password');
        let message = document.getElementById('message');
        let strength = document.getElementById('strength');

        password.addEventListener('input', function() {
            if (password.value.length > 0) {
                message.style.display = "block";
                message.style.color = "red";
            } else {
                message.style.display = "none";
            }
            if (password.value.length < 4) {
                strength.innerHTML = "weak";
            } else if (password.value.length > 8) {
                strength.innerHTML = "strong";
                message.style.color = "blue";
            }
        });
    </script>
</body>
</html>
```

## DOCTYPE and HTML Tag
The `<!DOCTYPE html>` declaration defines the document type and version of HTML. The `<html>` tag encloses the entire HTML document.

## Head Section
The `<head>` section contains meta-information about the document:
- `<meta charset="UTF-8">` sets the character encoding to UTF-8.
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` ensures the page is responsive on different devices.
- `<title>glotech-tutorials</title>` sets the title of the web page.
- `<link rel="stylesheet" href="style.css">` links to an external CSS file for styling.

## Body Section
The `<body>` section contains the content of the web page:
- `<div class="container">` is a container for the input box and message.
- `<div class="input-box">` contains the password input field and an image.
- `<input type="password" placeholder="password" id="password">` is the password input field with a placeholder text and an ID of "password".
- `<img src="image/right-arrow.png" alt="">` is an image element.
- `<p id="message">Your password strength is <span id="strength"></span></p>` is a paragraph that displays the password strength message. The `<span>` element with ID "strength" will be used to show the strength level.

## JavaScript

```javascript
let password = document.getElementById('password');
let message = document.getElementById('message');
let strength = document.getElementById('strength');

password.addEventListener('input', function() {
    if (password.value.length > 0) {
        message.style.display = "block";
        message.style.color = "red";
    } else {
        message.style.display = "none";
    }
    if (password.value.length < 4) {
        strength.innerHTML = "weak";
    } else if (password.value.length > 8) {
        strength.innerHTML = "strong";
        message.style.color = "blue";
    }
});
```

## Element Selection
The script selects the password input field, message paragraph, and strength span using `document.getElementById`.

## Event Listener
An event listener is added to the password input field to listen for the `input` event, which triggers whenever the user types in the password field.

## Password Strength Logic
- If the password field is not empty (`password.value.length > 0`), the message paragraph is displayed (`message.style.display = "block"`) and its color is set to red (`message.style.color = "red"`).
- If the password field is empty, the message paragraph is hidden (`message.style.display = "none"`).
- If the password length is less than 4 characters, the strength is set to "weak".
- If the password length is more than 8 characters, the strength is set to "strong" and the message color is changed to blue (`message.style.color = "blue"`).

## css code
```body{
    background-color: aliceblue;
    color: black;
}
.input-box input{
    height: 40px;
    width: 300px;
    outline: none;
    position: absolute;
    background: transparent;
    border-radius: 10px;
    font-weight: bold;
    font-size: 24px;
}
.input-box img{
    height: 45px;
    position: absolute;
    left: 50%;
    cursor: pointer;
}
#message{
    position: absolute;
    top: 10%;
    display: none;
}
```