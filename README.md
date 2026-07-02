<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Joe's First Website</title>
    <link rel="stylesheet" href="css2.css">
    <!-- <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-LN+7fdVzj6u52u30Kp6M/trliBMCMKTyK833zpbD+pXdCLuTusPj697FH4R/5mcr" crossorigin="anonymous">
     -->
    <!-- <link href="[cdn.jsdelivr.net](https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/css/bootstrap.min.css)" rel="stylesheet"> -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.7/dist/css/bootstrap.min.css" >
</head>
<body>
   <nav class="navbar navbar-dark bg-dark navbar-expand-lg fw-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Home</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link" aria-current="page" href="projects.html">Projects</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="aboutme.html">About me</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
    <h1>Welcome to My First Website!!!</h1>

    <div class="about">
        <p>Hi, I'm <strong>Joe Walker</strong>. I'm learning how to build websites using HTML, CSS, and JavaScript.</p>
        <p>This is my very first webpage. 🎉</p>
        <p>Check out my <a href="https://americanglass.us/about.php" target="_blank">Sales Page</a> or <a href="https://www.instagram.com/joe_blows_glass" target="_blank">Instagram</a> profile!</p>
    </div>

    <img src="https://i.pinimg.com/originals/16/a4/56/16a456a7d2fcbd9addc664458d2e1729.gif" alt="A photo of me" width="200">

    <div class="quote-box">
        <p id="quote">Click the button to get a quote!</p>
        <button type="button" class="btn btn-danger" onclick="newQuote()">New Quote</button>
    </div>

    <canvas id="snow"></canvas>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/bootstrap/5.3.8/js/bootstrap.min.js" integrity="sha512-nKXmKvJyiGQy343jatQlzDprflyB5c+tKCzGP3Uq67v+lmzfnZUi/ZT+fc6ITZfSC5HhaBKUIvr/nTLCV+7F+Q==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>    <!-- Snow Script -->
    <script>
    const canvas = document.getElementById('snow');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    let particles = [];

    for (let i = 0; i < 100; i++) {
        particles.push({
            x: Math.random() * canvas.width,
            y: Math.random() * canvas.height,
            r: Math.random() * 4 + 1,
            d: Math.random() * 1
        });
    }

    function drawSnow() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        ctx.fillStyle = "white";
        ctx.beginPath();
        for (let i = 0; i < particles.length; i++) {
            let p = particles[i];
            ctx.moveTo(p.x, p.y);
            ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2, true);
        }
        ctx.fill();
        update();
    }

    function update() {
        for (let i = 0; i < particles.length; i++) {
            let p = particles[i];
            p.y += p.d;
            if (p.y > canvas.height) {
                p.y = 0;
                p.x = Math.random() * canvas.width;
            }
        }
    }

    setInterval(drawSnow, 33);
    </script>

    <!-- Quote Script -->
    <script>
    const quotes = [
        "I live in a crazy time. - Anne Frank",
        "Two things are infinite: the universe and human stupidity; and I’m not sure about the former. - Einstein",
        "It's not a great wall. It's an alright wall I suppose. - Karl Pilkington",
        "I don’t know how to put this but, I’m kind of a big deal. - Ron Burgundy",
        "Real G's move in silence like lasagna. - Lil Wayne",
        "It is what it is til it ain’t. - Mac Miller"
    ];

    function newQuote() {
        const randomIndex = Math.floor(Math.random() * quotes.length);
        document.getElementById("quote").innerText = quotes[randomIndex];
    }
    </script>

</body>
</html>
