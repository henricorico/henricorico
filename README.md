<h1 align="center">👋 E aí,eu sou o Rico</h1>

<p align="center">
  <img src="https://i.imgur.com/1INYrlX.gif" alt="Goku gritando" width="800">
</p>

---

## 🚀 Sobre mim
- 💻 Serralheiro nas horas de dia, guerreiro dos infoprodutos à noite   
- 📚 Curto tecnologia, programação e projetos doidos com eletrônica  

---
## 🛠️ Minhas armas de batalha
![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
---
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)


## 📊 Estatísticas de guerra
<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=henricorico&show_icons=true&theme=tokyonight" alt="GitHub stats" height="165">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=henricorico&layout=compact&theme=tokyonight" alt="Top langs" height="165">
</p>

---

## 📈 Atividade
<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=henricorico&theme=tokyo-night" alt="Gráfico de atividades">
</p>

---
<!DOCTYPE html>
<html lang="pt-br">
<head>
<meta charset="UTF-8" />
<title>Jogo da Cobrinha - Rico Style</title>
<style>
  body { background: #111; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
  canvas { background: #222; display: block; margin: 0 auto; }
</style>
</head>
<body>
<canvas id="game" width="400" height="400"></canvas>
<script>
  const canvas = document.getElementById('game');
  const ctx = canvas.getContext('2d');
  const box = 20;
  let snake = [{x: 9 * box, y: 10 * box}];
  let direction = 'RIGHT';
  let food = {
    x: Math.floor(Math.random() * 20) * box,
    y: Math.floor(Math.random() * 20) * box
  };
  let score = 0;

  document.addEventListener('keydown', updateDirection);

  function updateDirection(event) {
    if(event.key === 'ArrowLeft' && direction !== 'RIGHT') direction = 'LEFT';
    else if(event.key === 'ArrowUp' && direction !== 'DOWN') direction = 'UP';
    else if(event.key === 'ArrowRight' && direction !== 'LEFT') direction = 'RIGHT';
    else if(event.key === 'ArrowDown' && direction !== 'UP') direction = 'DOWN';
  }

  function collision(head, array) {
    for(let i = 0; i < array.length; i++) {
      if(head.x === array[i].x && head.y === array[i].y) return true;
    }
    return false;
  }

  function draw() {
    ctx.fillStyle = '#111';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    for(let i = 0; i < snake.length; i++) {
      ctx.fillStyle = (i === 0) ? '#0f0' : '#0a0';
      ctx.fillRect(snake[i].x, snake[i].y, box, box);
      ctx.strokeStyle = '#020';
      ctx.strokeRect(snake[i].x, snake[i].y, box, box);
    }

    ctx.fillStyle = '#f00';
    ctx.fillRect(food.x, food.y, box, box);

    let snakeX = snake[0].x;
    let snakeY = snake[0].y;

    if(direction === 'LEFT') snakeX -= box;
    if(direction === 'UP') snakeY -= box;
    if(direction === 'RIGHT') snakeX += box;
    if(direction === 'DOWN') snakeY += box;

    if(snakeX === food.x && snakeY === food.y) {
      score++;
      food = {
        x: Math.floor(Math.random() * 20) * box,
        y: Math.floor(Math.random() * 20) * box
      };
    } else {
      snake.pop();
    }

    let newHead = {x: snakeX, y: snakeY};

    if(snakeX < 0 || snakeX >= canvas.width || snakeY < 0 || snakeY >= canvas.height || collision(newHead, snake)) {
      clearInterval(game);
      alert('Oxente, perdeu! Seu placar foi: ' + score);
    }

    snake.unshift(newHead);

    ctx.fillStyle = '#fff';
    ctx.font = '20px Arial';
    ctx.fillText('Placar: ' + score, 10, 390);
  }

  let game = setInterval(draw, 100);
</script>
</body>
</html>

## 💬 Frase de impacto
<p align="center">
  <b>"Faça seu dinheiro como quiser, ninguém vai na sua casa perguntar o que lhe falta."</b>
</p>

---

<p align="center">
  <i>nimonimonimonimo</i>
</p>