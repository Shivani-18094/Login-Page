# Login-Page
 <!DOCTYPE html>
<html lang="en">
<head>
    <title>Login Page</title>
    <link rel="stylesheet" href="Style.css" type="text/css">
</head>
<body>
    <div class="main">
        <div class="login">
            <h1>LOGIN PAGE</h1><br>
            <form id="login" method="post" onsubmit="return validateForm()">
                <label>Name :</label><br>
                <input type="text" placeholder="Enter your NAME" name="name" id="name">
                <br><br>
            
                <label>Email :</label><br>
                <input type="email" placeholder="Enter your email" name="email" id="n1">
                <br><br>
            
                <label>Phone NO. :</label><br>
                <input type="number" placeholder="Enter your Phone NO." name="phone" id="n2">
                <br><br>

                <label>Password :</label><br>
                <input type="password" placeholder="Enter your Password" name="password" id="n3">
                <br><br>

                <input type="submit" value="Submit" name="submit" id="submit">
            </form>
        </div>
    </div>
    <script>
        function validateForm(){
            var d = document.querySelector('#name').value;
            var a = document.querySelector('#n1').value;
            var b = document.querySelector('#n2').value;
            var c = document.querySelector('#n3').value;
            
            if(a === "" || b === "" || c === "" || d === "") {
                alert("All fields are required");
                return false; // Prevent form submission
            }
            else if(b.length !== 10) {
                alert("Number should be 10 Digits !");
                return false; // Prevent form submission
            }
            else if(isNaN(b)) {
                alert("Only numbers are allowed for Phone Number");
                return false; // Prevent form submission
            }
            else if(c.length <= 8) {
                alert("Password should be at least 8 characters long!");
                return false; // Prevent form submission
            }
            else if(!validateEmail(a)) {
                alert("Invalid email address");
                return false; // Prevent form submission
            }

            return true; // Allow form submission
        }

        function validateEmail(email) {
            // Regular expression for basic email validation
            var emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
            return emailRegex.test(email);
        }
    </script>
</body>
</html>


