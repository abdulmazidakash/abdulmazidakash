<hr/>

<div align="center">
  <h2>🐍 My Contributions 🐍</h2>
  <br>
  <img alt="snake eating my contributions" src="https://raw.githubusercontent.com/salesp07/salesp07/output/github-contribution-grid-snake.svg" />
  
  <br/><br/><br/>
</div>

<hr/>


<img align="right" src="https://visitor-badge.laobi.icu/badge?page_id=salesp07.salesp07" />

<h1 align="center">
    <img src="https://readme-typing-svg.herokuapp.com/?font=Righteous&size=35&center=true&vCenter=true&width=500&height=70&duration=4000&lines=Hi+There!+👋;+I'm+Abdul+Mazid+Akash!;" />
</h1>

<br/>

#### A passionate Web developer from Bangladesh



Skills: VUE JS / REACT / JS / HTML / CSS/MongoDB

- 🔭 I’m currently working on this page. 
- 👯 I’m looking to collaborate on GitHub 
- 💬 Ask me about Web Developing 


[<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/github.svg' alt='github' height='40'>](https://github.com/abdulmazidakash)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/linkedin.svg' alt='linkedin' height='40'>](https://www.linkedin.com/in/https://www.linkedin.com/in/abdulmazidakash//)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/facebook.svg' alt='facebook' height='40'>](https://www.facebook.com/https://www.facebook.com/akashabdulmazid/)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/instagram.svg' alt='instagram' height='40'>](https://www.instagram.com/https://www.instagram.com/abdulmazidakash//)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/twitter.svg' alt='twitter' height='40'>](https://twitter.com/https://x.com/abdulmazidakash)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/youtube.svg' alt='YouTube' height='40'>](https://www.youtube.com/channel/https://www.youtube.com/@abdulmazidakash)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/reddit.svg' alt='Reddit' height='40'>](https://www.reddit.com/user/https://www.reddit.com/user/abdulmazidakash/)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/icloud.svg' alt='website' height='40'>](https://abdulmazidakash.blogspot.com/)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/quora.svg' alt='quora' height='40'>](https://www.quora.com/profile/Abdul-Mazid-Akash)  [<img src='https://cdn.jsdelivr.net/npm/simple-icons@3.0.1/icons/pinterest.svg' alt='pinterest' height='40'>](https://www.pinterest.com/abdulmazidakash/)  



# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=abdulmazidakash&theme=midnight-purple&hide_border=false&include_all_commits=true&count_private=true)<br/>
![](https://github-readme-streak-stats.herokuapp.com/?user=abdulmazidakash&theme=midnight-purple&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=abdulmazidakash&theme=midnight-purple&hide_border=false&include_all_commits=true&count_private=true&layout=compact)

## 🏆 GitHub Trophies
![](https://github-profile-trophy.vercel.app/?username=abdulmazidakash&theme=discord_old_blurple&no-frame=false&no-bg=true&margin-w=4)

### 🔝 Top Contributed Repo
![](https://github-contributor-stats.vercel.app/api?username=abdulmazidakash&limit=5&theme=midnight-purple&combine_all_yearly_contributions=true)

---

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->

name: generate animation

on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */12 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the main branch
  push:
    branches:
    - main
    
  

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
