<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ProLactea Store - Carta Espacial</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Orbitron', sans-ser
  </style>
</head>
<body>
  <canvas id="stars"></canvas>
  <h1>🚀 Bienvenido a ProLactea Store</h1>
  <p>Tu portal hacia el universo del conocimiento y la observación astronómica 🌌</p>
  <button class="button" onclick="entrar()">Explorar Galaxia</button>

  <script>
    const canvas = document.getElementById("stars");
    const ctx = canvas.getContext("2d");
    let stars = [];

    function resize() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener("resize", resize);
    resize();

    for (let i = 0; i < 200; i++) {
      stars.push({
        x: Math.random() * canvas.width,
        y: Math.random() * canvas.height,
        radius: Math.random() * 1.5,
        speed: Math.random() * 0.5 + 0.2
      });
    }

    function animate() {
      ctx.fillStyle = "rgba(0,0,20,0.4)";
      ctx.fillRect(0, 0, canvas.width, canvas.height);

      ctx.fillStyle = "#ffffff";
      for (let s of stars) {
        ctx.beginPath();
        ctx.arc(s.x, s.y, s.radius, 0, Math.PI * 2);
        ctx.fill();

        s.y += s.speed;
        if (s.y > canvas.height) s.y = 0;
      }
      requestAnimationFrame(animate);
    }
    animate
    function entrar() {
      alert("🌠 Bienvenido explorador cósmico, pronto accederás a ProLactea Store...");
  </script>
</body>
</html>
