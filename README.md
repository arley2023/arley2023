<h1 align="center">
    <img src="https://readme-typing-svg.herokuapp.com/?font=Righteous&size=35&center=true&vCenter=true&width=500&height=70&duration=4000&lines=Olá!+👋;+Sou+Arley+Barros+dos+Santos!;" />
</h1>
<h3>Desenvolvedor Java-End </h3>

##

## Hi there 👋

<!--
**arley2023/arley2023** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

##
<div>
  <a href="https://github.com/arley2023"> 
<img height="42%" src="https://github-readme-stats.vercel.app/api?username=arley2023&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
  <img height="50%
" src="https://github-readme-stats.vercel.app/api/top-langs/?username=denisilvace&layout=compact&langs_count=16&theme=dark"/>
</div>

##

<div style="display: inline_block"><br>
  <img align="center" alt="Arley-Js" height="30" width="40" src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-plain.svg">
  <img align="center" alt="Arley-PHP" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/php/php-plain.svg">
  <img align="center" alt="Arley-Python" height="30" width="40" src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original-wordmark.svg">
 </div>

 ##
 <div>
  <a href="https://www.youtube.com/@Senacceoficial" target="_blank"><img src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white" target="_blank"></a>
  <a href="https://instagram.com/denis.p.silva" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white" target="_blank"></a>
 	<a href="https://www.twitch.tv/denispsilvace" target="_blank"><img src="https://img.shields.io/badge/Twitch-9146FF?style=for-the-badge&logo=twitch&logoColor=white" target="_blank"></a>
 <a href="https://discord.gg/236957863879114754" target="_blank"><img src="https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white" target="_blank"></a> 
  <a href = "mailto:denissilva@ce.senac.br"><img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
  <a href="https://www.linkedin.com/in/denissilvace" target="_blank"><img src="https://img.shields.io/badge/-LinkedIn-%230077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>   
</div>

##
# GitHub Action for generating a contribution graph with a snake eating your contributions.

# ![Snake animation](https://github.com/seuusuario/seuusuario/blob/output/github-contribution-grid-snake.svg)

name: Generate Snake

# Controls when the action will run.
on:
  schedule:
      # every 12 hours
    - cron: "0 */12 * * *"

  # This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:
  
  # Also run on every push on the master branch
  push:
    branches:
    - main

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      - name: Clone repo
        uses: actions/checkout@v3
    
      - name: Generate the snake files in './dist/'
        uses: Platane/snk@v3
        id: snake-gif
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |     
            dist/github-contribution-grid-snake.gif
            dist/github-contribution-grid-snake.svg
        env:
           GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

      - name: Show build status
        run: git status

      - name: Push new files to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
          commit_message: Update snake animations
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

