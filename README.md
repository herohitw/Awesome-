

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>You're Awesome</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(to right, #ffecd2, #fcb69f);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      color: #333;
    }

    .container {
      background-color: #fff;
      border-radius: 16px;
      padding: 30px;
      max-width: 420px;
      width: 90%;
      box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
      text-align: center;
    }

    h1 {
      margin-bottom: 20px;
      color: #ff4081;
      display: none;
    }

    input, button {
      padding: 10px;
      font-size: 16px;
      width: 80%;
      margin-bottom: 15px;
      border-radius: 8px;
    }

    input {
      border: 1px solid #ccc;
    }

    button {
      background-color: #ff6f61;
      color: white;
      border: none;
      cursor: pointer;
    }

    #linkOutput {
      font-size: 14px;
      word-wrap: break-word;
    }

    .ad-box {
      background: #f3f3f3;
      padding: 10px;
      border: 2px dashed #bbb;
      border-radius: 8px;
      margin-top: 20px;
      color: #888;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1 id="greeting">You're Awesome!</h1>

    <div id="inputSection">
      <input type="text" id="newName" placeholder="Enter your name">
      <br>
      <button onclick="generateGreeting()">Make It Awesome</button>
    </div>

    <p id="linkOutput"></p>

    <div class="ad-box">
      <!-- Adsterra Ad Placeholder -->
      Your Ad Goes Here (paste Adsterra code)
    </div>
  </div>

  <script>
    const greeting = document.getElementById("greeting");
    const inputSection = document.getElementById("inputSection");
    const params = new URLSearchParams(window.location.search);
    const name = params.get("name");

    if (name) {
      greeting.innerText = "Hey " + name + ", you're awesome!";
      greeting.style.display = "block";
      inputSection.style.display = "none";
    }

    function generateGreeting() {
      const newName = document.getElementById("newName").value.trim();
      if (!newName) {
        alert("Please enter a name.");
        return;
      }
      const newURL = window.location.origin + window.location.pathname + "?name=" + encodeURIComponent(newName);
      greeting.innerText = "Hey " + newName + ", you're awesome!";
      greeting.style.display = "block";
      document.getElementById("linkOutput").innerHTML = "Share this link: <br><a href='" + newURL + "' target='_blank'>" + newURL + "</a>";
      inputSection.style.display = "none";
    }
  </script>
</body>
</html>