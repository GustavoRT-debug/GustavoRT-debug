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

---

```yaml
# Nome da Actions:
name: Snake Game

# Controlador do tempo que será feito a atualização dos arquivos.
on:
  schedule:
    # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

  # Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

      # Repositório que será utilizado para gerar os arquivos.
      - name: Generate Snake Game files
        id: snake-gif
        uses: Platane/snk@master
        with:
          github_user_name: GustavoRT-debug
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      # Para as atualizações.
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      # Atualização da página do GitHub
      - name: Deploy to GitHub Pages
        uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # o branch de saída que mencionamos acima
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}




