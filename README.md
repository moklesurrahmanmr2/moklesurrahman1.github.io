# moklesurrahman1.github.io
<!DOCTYPE html>
<html>
<head>
    <title>Student Eligibility Check</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            font-family: Arial;
            margin: 30px;
        }
        .box {
            padding: 15px;
            border: 1px solid #ddd;
            width: 400px;
        }
        .result {
            font-size: 20px;
            font-weight: bold;
            margin-top: 10px;
        }
    </style>
</head>

<body>

<h2>Student Eligibility Check</h2>

<div class="box">

<p><b>Student ID:</b> P12345</p>
<p><b>Email:</b> student@gmail.com</p>
<p><b>City:</b> Los Angeles</p>
<p><b>ZIP:</b> 90001</p>
<p><b>Phone:</b> 123456789</p>
<p><b>Populi Name:</b> John Doe</p>
<p><b>Course Abbrv:</b> CS101</p>

<div class="result" id="status"></div>

</div>

<br>

<h3>Eligibility Chart</h3>
<canvas id="myChart" width="400" height="200"></canvas>

<script>
// ===== Eligibility Check =====
let city = "Los Angeles";

let statusText = "";

if (city === "Los Angeles") {
    statusText = "Eligible";
} else {
    statusText = "Not Eligible";
}

document.getElementById("status").innerHTML = "Status: " + statusText;


// ===== Chart =====
let eligibleCount = (statusText === "Eligible") ? 1 : 0;
let notEligibleCount = (statusText === "Not Eligible") ? 1 : 0;

new Chart(document.getElementById("myChart"), {
    type: "bar",
    data: {
        labels: ["Eligible", "Not Eligible"],
        datasets: [{
            label: "Student Status",
            data: [eligibleCount, notEligibleCount]
        }]
    }
});
</script>

</body>
</html>
