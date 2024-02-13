### E aí, sou o Gustavo Torres! 👋

<div align="center">
  <a href="https://github.com/GustavoRT-debug">
    <img height="180em" src="https://github-readme-stats.vercel.app/api?username=GustavoRT-debug&show_icons=true&theme=dracula&include_all_commits=true&count_private=true"/>
    <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=GustavoRT-debug&layout=compact&langs_count=7&theme=dracula"/>
  </a>
</div>

<div align="center">
  <img src="https://www.elo.net.br/wp-content/uploads/2021/05/bittrainers_web-01.png" alt="Logo da BitTrainers" width="200px"/>
</div>

### 👨‍💼 Sou estagiário na BitTrainers, aprontando muitas coisas legais!

### Um pouquinho sobre mim:

- 🚀 Louco por código e tecnologia.
- 🎓 Estudante de Ciência da Computação.
- 💻 Atualmente explorando o vasto universo do desenvolvimento de software.

## 🛠️ Ferramentas e Tecnologias que uso para bagunçar o código:

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)
![C#](https://img.shields.io/badge/-C%23-239120?style=flat-square&logo=c-sharp&logoColor=white)
![Java](https://img.shields.io/badge/-Java-007396?style=flat-square&logo=java&logoColor=white)
![C](https://img.shields.io/badge/-C-00599C?style=flat-square&logo=c&logoColor=white)
![C++](https://img.shields.io/badge/-C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![Ruby](https://img.shields.io/badge/-Ruby-CC342D?style=flat-square&logo=ruby&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

## 🚀 Projetos que aprontei:

### Projeto 1: 🐍🎮 Jogo da Cobrinha em Python
Descrição: Um clássico jogo da cobrinha feito em Python usando a biblioteca Pygame.
[Repositório](https://github.com/GustavoRT-debug/jogo-da-cobrinha-python)

### Projeto 2: 💻 Calculadora Científica em C#
Descrição: Uma calculadora com funcionalidades avançadas feita em C#.
[Repositório](https://github.com/GustavoRT-debug/calculadora-csharp)

## 📫 Bora bater um papo?

- [YouTube](https://www.youtube.com/channel/UCs517mniohfXVermU2ZptFQ)
- [LinkedIn](https://www.linkedin.com/in/gustavo-ramos-lages-torres-b9b700170/)

## 😄 É isso aí, bora codar e se divertir!  

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Snake Commits</title>
    <style>
        canvas {
            display: block;
            margin: 0 auto;
            background-color: #f0f0f0;
        }
    </style>
</head>
<body>
    <canvas id="gameCanvas" width="400" height="400"></canvas>
    <script>
        const canvas = document.getElementById("gameCanvas");
        const ctx = canvas.getContext("2d");

        const box = 20;
        let snake = [{ x: 10 * box, y: 10 * box }];
        let food = { x: Math.floor(Math.random() * 20) * box, y: Math.floor(Math.random() * 20) * box };
        let score = 0;

        document.addEventListener("keydown", direction);

        let d;
        function direction(event) {
            if (event.keyCode == 37 && d != "RIGHT") {
                d = "LEFT";
            } else if (event.keyCode == 38 && d != "DOWN") {
                d = "UP";
            } else if (event.keyCode == 39 && d != "LEFT") {
                d = "RIGHT";
            } else if (event.keyCode == 40 && d != "UP") {
                d = "DOWN";
            }
        }

        function collision(head, array) {
            for (let i = 0; i < array.length; i++) {
                if (head.x == array[i].x && head.y == array[i].y) {
                    return true;
                }
            }
            return false;
        }

        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);

            for (let i = 0; i < snake.length; i++) {
                ctx.fillStyle = (i === 0) ? "green" : "white";
                ctx.fillRect(snake[i].x, snake[i].y, box, box);
                ctx.strokeStyle = "black";
                ctx.strokeRect(snake[i].x, snake[i].y, box, box);
            }

            ctx.fillStyle = "red";
            ctx.fillRect(food.x, food.y, box, box);

            let snakeX = snake[0].x;
            let snakeY = snake[0].y;

            if (d == "LEFT") snakeX -= box;
            if (d == "UP") snakeY -= box;
            if (d == "RIGHT") snakeX += box;
            if (d == "DOWN") snakeY += box;

            if (snakeX == food.x && snakeY == food.y) {
                score++;
                food = { x: Math.floor(Math.random() * 20) * box, y: Math.floor(Math.random() * 20) * box };
            } else {
                snake.pop();
            }

            const newHead = { x: snakeX, y: snakeY };

            if (snakeX < 0 || snakeX >= canvas.width || snakeY < 0 || snakeY >= canvas.height || collision(newHead, snake)) {
                clearInterval(game);
                alert("Game Over! Your score: " + score);
                location.reload();
            }

            snake.unshift(newHead);

            ctx.fillStyle = "black";
            ctx.font = "30px Arial";
            ctx.fillText(score, 2 * box, 1.6 * box);
        }

        let game = setInterval(draw, 100);
    </script>
</body>
</html>

