# cathaypacificptfs.github.io
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Cathay Pacific Booking Demo</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,Helvetica,sans-serif;
}

body{
    background:linear-gradient(rgba(0,80,85,.55),rgba(0,80,85,.55)),
    url("https://images.unsplash.com/photo-1436491865332-7a61a109cc05?auto=format&fit=crop&w=1600&q=80");
    background-size:cover;
    background-position:center;
    background-repeat:no-repeat;
    min-height:100vh;
}

header{
    background:#006564;
    color:white;
    text-align:center;
    padding:20px;
}

.container{
    width:90%;
    max-width:450px;
    margin:40px auto;
    background:white;
    padding:25px;
    border-radius:12px;
    box-shadow:0 10px 25px rgba(0,0,0,.3);
}

h2{
    text-align:center;
    color:#006564;
    margin-bottom:20px;
}

label{
    display:block;
    margin-top:15px;
    font-weight:bold;
}

input,select{
    width:100%;
    padding:10px;
    margin-top:5px;
    border:1px solid #ccc;
    border-radius:6px;
    font-size:15px;
}

button{
    width:100%;
    margin-top:18px;
    padding:12px;
    border:none;
    border-radius:6px;
    font-size:16px;
    cursor:pointer;
}

.search{
    background:#006564;
    color:white;
}

.book{
    background:#00a86b;
    color:white;
    display:none;
}

button:hover{
    opacity:.9;
}

#results,#confirmation{
    display:none;
    margin-top:20px;
    padding:15px;
    border-radius:8px;
}

#results{
    background:#eef7f6;
}

#confirmation{
    background:#d4edda;
    color:#155724;
}

footer{
    color:white;
    text-align:center;
    margin:30px;
}
</style>
</head>

<body>

<header>
<h1>Cathay Pacific Booking Demo</h1>
<p>Educational Mock Booking Website</p>
</header>

<div class="container">

<h2>Book Your Flight</h2>

<label>From</label>
<input type="text" id="from" placeholder="Hong Kong">

<label>To</label>
<input type="text" id="to" placeholder="Tokyo">

<label>Departure Date</label>
<input type="date" id="date">

<label>Passengers</label>
<select id="passengers">
<option>1 Adult</option>
<option>2 Adults</option>
<option>3 Adults</option>
<option>4 Adults</option>
</select>

<label>Cabin Class</label>
<select id="cabin">
<option>Economy</option>
<option>Premium Economy</option>
<option>Business</option>
<option>First</option>
</select>

<button class="search" onclick="searchFlights()">
Search Flights
</button>

<div id="results"></div>

<button class="book" id="bookButton" onclick="bookFlight()">
Book Flight
</button>

<div id="confirmation"></div>

</div>

<footer>
© 2026 Educational Demo
</footer>

<script>

function searchFlights(){

const from=document.getElementById("from").value.trim();
const to=document.getElementById("to").value.trim();
const date=document.getElementById("date").value;
const passengers=document.getElementById("passengers").value;
const cabin=document.getElementById("cabin").value;

if(!from || !to || !date){
    alert("Please complete all fields.");
    return;
}

document.getElementById("confirmation").style.display="none";

document.getElementById("results").style.display="block";
document.getElementById("bookButton").style.display="block";

document.getElementById("results").innerHTML=`
<h3>Flight Available</h3>
<p><strong>Route:</strong> ${from} ➜ ${to}</p>
<p><strong>Date:</strong> ${date}</p>
<p><strong>Passengers:</strong> ${passengers}</p>
<p><strong>Cabin:</strong> ${cabin}</p>
<p><strong>Estimated Fare:</strong> HK$4,850</p>
`;
}

function bookFlight(){

const booking="CX"+Math.floor(Math.random()*900000+100000);

document.getElementById("confirmation").style.display="block";

document.getElementById("confirmation").innerHTML=`
<h2>✅ Booking Confirmed!</h2>
<p>Your demo booking has been completed successfully.</p>
<p><strong>Booking Reference:</strong> ${booking}</p>
<p>A confirmation email would normally be sent to you.</p>
`;
}

</script>

</body>
</html>
