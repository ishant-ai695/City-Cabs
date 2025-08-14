<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>City Cabs Gurugram</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f5f5f5;
      text-align: center;
      padding: 20px;
    }
    header {
      background: #0077b6;
      color: white;
      padding: 15px;
      font-size: 1.5em;
      border-radius: 10px;
    }
    .container {
      background: white;
      padding: 20px;
      border-radius: 10px;
      max-width: 400px;
      margin: auto;
      box-shadow: 0px 4px 8px rgba(0,0,0,0.1);
    }
    select, input {
      width: 100%;
      padding: 10px;
      margin: 8px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
      font-size: 1em;
    }
    button {
      width: 100%;
      padding: 12px;
      background: #0077b6;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 1.1em;
      cursor: pointer;
    }
    button:hover {
      background: #023e8a;
    }
    .result {
      margin-top: 15px;
      font-size: 1.2em;
      font-weight: bold;
    }
    .whatsapp {
      background: #25d366;
      margin-top: 10px;
    }
    .whatsapp:hover {
      background: #128c7e;
    }
  </style>
</head>
<body>

<header>🚖 City Cabs – Gurugram</header>

<div class="container">
  <h2>Fare Calculator</h2>
  
  <label for="car">Select Car Type:</label>
  <select id="car">
    <option value="12">Dzire (4+1) – ₹12/km</option>
    <option value="10">WagonR (4+1) – ₹10/km</option>
    <option value="15">Ertiga (6+1) – ₹15/km</option>
    <option value="18">Innova Crysta (6+1) – ₹18/km</option>
  </select>

  <label for="distance">Enter Distance (km):</label>
  <input type="number" id="distance" placeholder="e.g. 25">

  <button onclick="calculateFare()">Calculate Fare</button>
  <div class="result" id="fareResult"></div>

  <button class="whatsapp" onclick="sendWhatsApp()">📲 Book on WhatsApp</button>
</div>

<script>
  let selectedFare = 0;

  function calculateFare() {
    const rate = parseFloat(document.getElementById('car').value);
    const distance = parseFloat(document.getElementById('distance').value);
    if (!distance || distance <= 0) {
      document.getElementById('fareResult').innerText = "Please enter valid distance.";
      return;
    }
    selectedFare = rate * distance;
    document.getElementById('fareResult').innerText = Estimated Fare: ₹${selectedFare};
  }

  function sendWhatsApp() {
    const rate = document.getElementById('car').value;
    const carName = document.getElementById('car').options[document.getElementById('car').selectedIndex].text;
    const distance = document.getElementById('distance').value;

    if (!distance || distance <= 0) {
      alert("Please enter distance first.");
      return;
    }

    const message = Hello City Cabs,%0AI want to book:%0ACar: ${carName}%0ADistance: ${distance} km%0AEstimated Fare: ₹${selectedFare};
    window.open(https://wa.me/919416273735?text=${message}, '_blank');
  }
</script>

</body>
</html>
