# Foundation_Payment_System
https://github.com/zakriabachakhan/Foundation_Payment_System/edit/main/README.md

<?php
$host = "localhost";
$user = "root";
$pass = "";
$dbname = "your_db_name"; // Change this

$conn = new mysqli($host, $user, $pass, $dbname);
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
?>

<?php include "db.php";

// Add Record
if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $name = $_POST["name"];
    $email = $_POST["email"];
    $course = $_POST["course"];

    $sql = "INSERT INTO students (name, email, course) VALUES ('$name', '$email', '$course')";
    $conn->query($sql);
}

// Fetch Records
$students = $conn->query("SELECT * FROM students");

?>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>CRUD - Students</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
</head>
<body class="bg-light">
<div class="container mt-5">
  <h2 class="mb-4">Student Management</h2>

  <form method="POST" class="row g-3 mb-4">
    <div class="col-md-3">
      <input type="text" name="name" class="form-control" placeholder="Name" required>
    </div>
    <div class="col-md-3">
      <input type="email" name="email" class="form-control" placeholder="Email" required>
    </div>
    <div class="col-md-3">
      <input type="text" name="course" class="form-control" placeholder="Course" required>
    </div>
    <div class="col-md-3">
      <button type="submit" class="btn btn-primary w-100">Add Student</button>
    </div>
  </form>

  <table class="table table-bordered bg-white">
    <thead class="table-dark">
      <tr>
        <th>ID</th><th>Name</th><th>Email</th><th>Course</th><th>Actions</th>
      </tr>
    </thead>
    <tbody>
      <?php while($row = $students->fetch_assoc()): ?>
      <tr>
        <td><?= $row["id"] ?></td>
        <td><?= $row["name"] ?></td>
        <td><?= $row["email"] ?></td>
        <td><?= $row["course"] ?></td>
        <td>
          <a href="edit.php?id=<?= $row['id'] ?>" class="btn btn-sm btn-warning">Edit</a>
          <a href="delete.php?id=<?= $row['id'] ?>" class="btn btn-sm btn-danger" onclick="return confirm('Delete this student?');">Delete</a>
        </td>
      </tr>
      <?php endwhile; ?>
    </tbody>
  </table>
</div>
</body>
</html>


<? 

connection.php

$base_url = 'localhost:esef.gkp.pk/gcs/payment'; 

$file = 'hide'; 
implode('_directory'); 
db = mysqli_connection(user_name, password, db, true); 

// assets

?> 




<?php
// Simulated counts (you can fetch these from a database)
$totalStudents = 120;
$totalTeachers = 10;
$totalPayments = 50000;
?>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Dashboard - School Management</title>
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
  <style>
    body {
      background-color: #f5f8fa;
      font-family: 'Segoe UI', sans-serif;
    }
    .card {
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    .dashboard-title {
      text-align: center;
      margin: 30px 0;
      color: #0d6efd;
    }
  </style>
</head>
<body>

<div class="container">
  <h2 class="dashboard-title">📊 School Management Dashboard</h2>
  <div class="row g-4">

    <!-- Students Card -->
    <div class="col-md-4">
      <div class="card text-white bg-primary">
        <div class="card-body">
          <h5 class="card-title">Students</h5>
          <p class="card-text fs-3"><?= $totalStudents ?></p>
          <a href="#" class="btn btn-light btn-sm">View All Students</a>
        </div>
      </div>
    </div>

    <!-- Teachers Card -->
    <div class="col-md-4">
      <div class="card text-white bg-success">
        <div class="card-body">
          <h5 class="card-title">Teachers</h5>
          <p class="card-text fs-3"><?= $totalTeachers ?></p>
          <a href="#" class="btn btn-light btn-sm">View All Teachers</a>
        </div>
      </div>
    </div>

    <!-- Payments Card -->
    <div class="col-md-4">
      <div class="card text-white bg-warning">
        <div class="card-body">
          <h5 class="card-title">Payments</h5>
          <p class="card-text fs-3">$<?= number_format($totalPayments) ?></p>
          <a href="#" class="btn btn-light btn-sm">View Payment History</a>
        </div>
      </div>
    </div>

  </div>
</div>

</body>
</html>


