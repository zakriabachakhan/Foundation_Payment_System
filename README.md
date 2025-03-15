# Foundation_Payment_System
https://github.com/zakriabachakhan/Foundation_Payment_System/edit/main/README.md

<? 

connection.php

$base_url = 'localhost:esef.gkp.pk/gcs/payment'; 

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


