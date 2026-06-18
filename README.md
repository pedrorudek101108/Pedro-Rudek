<h1 align="center">Olá! 👋 Eu sou Pedro Rudek</h1>

<p align="center">
🎓 Estudante de Engenharia de Software na Unicesumar <br>
💻 Focado em Python e Desenvolvimento de Software
</p>

---

## 🚀 Sobre mim

- 🎓 Cursando Engenharia de Software na Unicesumar
- 🐍 Estudando Python
- 📚 Aprendendo Git, GitHub e Banco de Dados
- 💼 Em busca da minha primeira oportunidade na área de tecnologia
- 🚀 Sempre disposto a aprender novas tecnologias

---

## 💻 Tecnologias que estou aprendendo

<div> 
  <a href="https://instagram.com/pedrorudek" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
  <a href = "mailto:pedrorudek87@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/pedro-rudek-rodrigues-b91b603b2 " target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a> 
  
</div>
---



## 🎯 Objetivos para 2026

- ✅ Aprender Python
- ✅ Criar projetos para meu portfólio
- ✅ Contribuir para projetos no GitHub
- ✅ Conseguir um estágio em Desenvolvimento de Software

---

### 📫 Contato

GitHub: https://github.com/Pedro-Rudek

⭐ Obrigado por visitar meu perfil!



name: Generate Snake

on:
  # Executa automaticamente a cada 24 horas
  schedule:
    - cron: "0 0 * * *"
  
  # Permite executar manualmente a qualquer momento
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      # Gera a animação da cobrinha a partir das contribuições
      - name: generate github-contribution-grid-snake
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
          
      # Envia os arquivos gerados para a branch 'output'
      - name: push github-contribution-grid-snake to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

