- 👋 Hi, I’m @marianalmd
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
marianalmd/marianalmd is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>p5.js Animation</title>
  <link rel="stylesheet" href="style.css">
  <script src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.0/p5.js"></script>
  <script src="sketch.js" defer></script>
</head>
<body>
  <h1>p5.js Animation</h1>
  <p>Este é um projeto simples de animação usando p5.js.</p>
</body>
</html>
let circles = [];

function setup() {
  createCanvas(800, 600);
  for (let i = 0; i < 10; i++) {
    circles.push({
      x: random(width),
      y: random(height),
      xSpeed: random(-2, 2),
      ySpeed: random(-2, 2),
      diameter: random(20, 50),
      color: color(random(255), random(255), random(255))
    });
  }
}

function draw() {
  background(0);
  for (let i = 0; i < circles.length; i++) {
    let circle = circles[i];
    circle.x += circle.xSpeed;
    circle.y += circle.ySpeed;
    if (circle.x > width || circle.x < 0) {
      circle.xSpeed *= -1;
    }
    if (circle.y > height || circle.y < 0) {
      circle.ySpeed *= -1;
    }
    fill(circle.color);
    noStroke();
    ellipse(circle.x, circle.y, circle.diameter);
  }
}
body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #333;
  color: #fff;
  margin: 0;
  padding: 0;
}
h1 {
  margin-top: 20px;
}
