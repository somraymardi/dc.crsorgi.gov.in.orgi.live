# dc.crsorgi.gov.in.orgi.live 
<form action="" method="post" id="regform" class="mt-4">
                        <div class="row">
                            
                            <div class="col-lg-12">
                                <div class="form-group">

            
                        <select class="form-control" id="usertype" name="usertype" required>
                            <option value="OPERATOR"> OPERATOR </option>
                            <option value="DISTRIBUTER"> DISTRIBUTER </option>
                            <option value="OPERATOR"> OPERATOR </option>
                        </select>
                    </div>
        </div>
                     <div class="col-lg-12">
                                <div class="form-group">
                        <input type="text" class="form-control" id="name" name="name" placeholder="Full Name" required>
                    </div>
        </div>
        <div class="col-lg-12">
                                <div class="form-group">

                        <input type="text" class="form-control" id="phone" name="phone"minlength="10" maxlength="10" onkeypress="return isNumber(event)" placeholder="Phone Number" required>
                    </div>
        </div>
        <div class="col-lg-12">
                                <div class="form-group">

                        <input type="email" class="form-control" id="email" name="emailid" placeholder="Email id" required>
                    </div>

                </div>
                <div class="col-lg-12">
                                <div class="form-group">

                    
                        <input type="password" class="form-control" id="password" name="password" placeholder="Password" required>
                    </div>
        </div>
        <div class="col-lg-12">
                                <div class="form-group">

                        <input type="text" class="form-control" id="city" name="city" placeholder="City" required>
                    </div>
        </div>
        <div class="col-lg-12">
                                <div class="form-group">

                        <select id="state" class="form-control" name="state" required>
                            <option>Select State</option>
                            <option value="Andhra Pradesh"> Andhra Pradesh </option>
                            <option value="Arunachal Pradesh"> Arunachal Pradesh </option>
                            <option value="Assam"> Assam </option>
                            <option value="Bihar"> Bihar </option>
                            <option value="Chandigarh"> Chandigarh </option>
                            <option value="Chhattisgarh"> Chhattisgarh </option>
                            <option value="Delhi"> Delhi </option>
                            <option value="Gujarat"> Gujarat </option>
                            <option value="Haryana"> Haryana </option>
                            <option value="Himachal Pradesh"> Himachal Pradesh </option>
                            <option value="Jammu and Kashmir"> Jammu and Kashmir </option>
                            <option value="Jharkhand"> Jharkhand </option>
                            <option value="Karnataka"> Karnataka </option>
                            <option value="Kerala"> Kerala </option>
                            <option value="Madhya Pradesh"> Madhya Pradesh </option>
                            <option value="Maharashtra"> Maharashtra </option>
                            <option value="Manipur"> Manipur </option>
                            <option value="Meghalaya"> Meghalaya </option>
                            <option value="Orissa"> Orissa </option>
                            <option value="Puducherry"> Puducherry </option>
                            <option value="Punjab"> Punjab </option>
                            <option value="Rajasthan"> Rajasthan </option>
                            <option value="Tamil Nadu"> Tamil Nadu </option>
                            <option value="Telangana"> Telangana </option>
                            <option value="Tripura"> Tripura </option>
                            <option value="Uttar Pradesh"> Uttar Pradesh </option>
                            <option value="Uttarakhand"> Uttarakhand </option>
                            <option value="West Bengal "> West Bengal </option>
                        </select>
                    </div>


                </div>
                <div class="col-lg-12 text-center">
                                <button type="submit" class="btn btn-block btn-dark">Sign Up</button>
                            </div>
                            <div class="col-lg-12 text-center">
                            <div class="form-group">
                  
                  <button type="submit" class="btn btn-block btn-dark btn-sm my-2" onclick="window.location.href='login.php';">
                  Already have an account? Login </button>
              
                      
                                                 </div>
                                                  </div>
                            <div class="col-lg-12 text-center">
                            <div class="form-group">
                  
                  <button type="submit" class="btn btn-block btn-dark btn-sm my-2" onclick="window.location.href='https://pgecm.in/';">
                  BUY SOURCE CODE </button>
              <?php
// Database connection
$servername = "localhost";
$username = "root";
$password = "";
$dbname = "your_database_name";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
  die("Connection failed: " . $conn->connect_error);
}

if ($_SERVER["REQUEST_METHOD"] == "POST") {
  // Get user inputs from the form
  $name = $_POST['name'];
  $email = $_POST['email'];
  $password = $_POST['password'];

  // Hash the password for security
  $hashed_password = password_hash($password, PASSWORD_DEFAULT);

  // SQL query to insert data into the database
  $sql = "INSERT INTO users (name, email, password) VALUES ('$name', '$email', '$hashed_password')";

  if ($conn->query($sql) === TRUE) {
    echo "New record created successfully";
  } else {
    echo "Error: " . $sql . "<br>" . $conn->error;
  }
}

$conn->close();
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>User Signup</title>
</head>
<body>

<h2>Signup Form</h2>
<form method="post" action="signup.php">
    Name: <input type="text" name="name" required><br><br>
    Email: <input type="email" name="email" required><br><br>
    Password: <input type="password" name="password" required><br><br>
    <input type="submit" value="Signup">
</form>

</body>
</html>
