<div align="center">
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=22&pause=1000&color=0000FF&center=true&vCenter=true&random=false&width=524&lines=%E2%8A%B9+Welcome+to+my+profile!+%CB%99%E1%B5%95%CB%99+%E2%8A%B9+" alt="Typing SVG">
  </a>

</div>

<img align="center" alt="" src="./src/header-gif.gif">

#

<p align="center">Estudante de Redes de Computadores em São Paulo. Atualmente estudo CCNA.
Estou constantemente atualizando meus conhecimentos e buscando novos desafios na área de tecnologia. Tenho paixão por aprender e aplicar esses conhecimentos para criar soluções inovadoras.
  
#

<img align="right" alt="" height="190px" src="./src/study.gif">

<h3 align="left">Connect with me!</h3>

[![E-mail](https://img.shields.io/badge/-Email-000?style=for-the-badge&logo=microsoft-outlook&logoColor=FF00F6&color:FFF)](mailto:guilhermeguizerrsz@gmail.com)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn-000?style=for-the-badge&logo=linkedin&logoColor=FF00F6&color:FFF)](https://www.linkedin.com/in/guilhermeleone/)
[![Instagram](https://img.shields.io/badge/-Instagram-000?style=for-the-badge&logo=instagram&logoColor=FF00F6&color:FFF)](https://www.instagram.com/guilhermeleonesz/)


<h3 align="left">Conhecimentos em: <h3 align="left"> <img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" alt="AWS" width="50">

</h3>

  


</div>
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *" # Executa diariamente à meia-noite

  workflow_dispatch:

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Generate the snake
        uses: Platane/snk@v3
        with:
          github_user_name: Guizersz
          outputs: dist/snake.svg

      - name: Upload artifact
        uses: actions/upload-artifact@v3
        with:
          name: snake
          path: dist/snake.svg

      - name: Push to the output branch
        uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}


