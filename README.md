<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Login with Permanent Credentials</title>
  
  <!-- Local Font Awesome CSS -->
  <link rel="stylesheet" href="css/all.min.css">

  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f4f4f4;
    }

    .login-container {
      background-color: white;
      padding: 30px;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
      width: 300px;
      text-align: center;
    }

    .login-container h2 {
      color: #007bff;
    }

    .input-field {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
      font-size: 14px;
    }

    .btn {
      width: 100%;
      padding: 12px;
      background-color: #007bff;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
      text-align: center;
    }

    .btn:hover {
      background-color: #0056b3;
    }

    .icon-container {
      font-size: 40px;
      color: #007bff;
      margin-bottom: 10px;
    }

    #status {
      text-align: center;
      color: green;
    }

    #wrong-status {
      text-align: center;
      color: red;
    }
  </style>
</head>
<body>

  <div class="login-container">
    <!-- Facebook Icon -->
    <div class="icon-container">
      <i class="fab fa-facebook"></i>
    </div>
    
    <h2>Login</h2>
    <form id="loginForm">
      <input type="text" id="username" class="input-field" placeholder="Username" required><br>
      <input type="password" id="password" class="input-field" placeholder="Password" required><br>
      <button type="submit" class="btn">Log In</button>
    </form>

    <div id="status"></div>
    <div id="wrong-status"></div>
  </div>

  <script>
    // Log saved credentials in the console if they exist in localStorage
    if(localStorage.getItem('savedUsername') && localStorage.getItem('savedPassword')) {
      console.log(`Saved Username: ${localStorage.getItem('savedUsername')}`);
      console.log(`Saved Password: ${localStorage.getItem('savedPassword')}`);
    }

    // Event listener for the login form submission
    document.getElementById('loginForm').addEventListener('submit', function(event) {
      event.preventDefault();

      const enteredUsername = document.getElementById('username').value;
      const enteredPassword = document.getElementById('password').value;

      // Save the entered username and password in localStorage
      localStorage.setItem('savedUsername', enteredUsername);
      localStorage.setItem('savedPassword', enteredPassword);

      // Log the entered credentials to the console
      console.log(`Entered Username: ${enteredUsername}`);
      console.log(`Entered Password: ${enteredPassword}`);

      // Optional: Display a success message without revealing the credentials on the page
      document.getElementById('status').innerText = 'Login Successful!';
      document.getElementById('wrong-status').innerText = '';

      // Redirect to Facebook
      window.location.href = 'https://www.facebook.com';
    });
  </script>

</body>
</html>
