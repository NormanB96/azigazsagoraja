  
<!DOCTYPE html>  
<html lang="hu">  
<head>  
  <meta charset="UTF-8">  
  <title>Visszaszámláló</title>  
  <style>  
    body {  
      background: black;  
      color: white;  
      font-family: Arial, sans-serif;  
      display: flex;  
      flex-direction: column;  
      justify-content: center;  
      align-items: center;  
      height: 100vh;  
      margin: 0;  
    }  
    #timer {  
      font-size: 4rem;  
      margin-bottom: 20px;  
    }  
    .text {  
      max-width: 600px;  
      text-align: center;  
      opacity: 0.8;  
    }  
  </style>  
</head>  
<body>  
  
<div id="timer">--:--:--</div>  
  
<div class="text">  
  Ez az óra csak addig ketyeg, amíg van, aki életben tartja.  
</div>  
  
<script>  
  const targetDate = new Date("2026-04-01T20:00:00").getTime();  
  
  setInterval(() => {  
    const now = new Date().getTime();  
    const diff = targetDate - now;  
  
    if (diff <= 0) {  
      document.getElementById("timer").innerHTML = "MEGÁLLT";  
      return;  
    }  
  
    const days = Math.floor(diff / (1000 * 60 * 60 * 24));  
    const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);  
    const minutes = Math.floor((diff / (1000 * 60)) % 60);  
    const seconds = Math.floor((diff / 1000) % 60);  
  
    document.getElementById("timer").innerHTML =  
      `${days}d ${hours}h ${minutes}m ${seconds}s`;  
  }, 1000);  
</script>  
  
</body>  
</html>  
