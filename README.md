## Hi there 👋
<img src="/src/header_.png">
# .github/workflows/update-readme.yml
name: Update README

on:
  schedule:
    # 每小时执行一次 (UTC时间)
    - cron: '0 * * * *'
  workflow_dispatch: # 允许手动触发

jobs:
  update-readme:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Update README
        run: |
          # 获取当前时间
          current_time=$(TZ='Asia/Shanghai' date '+%Y-%m-%d %H:%M:%S')
          
          # 更新 README.md 中的时间
          sed -i "s/<!-- TIME_PLACEHOLDER -->.*/<!-- TIME_PLACEHOLDER -->**Last updated:** $current_time (GMT+8)/" README.md
          
      - name: Commit changes
        run: |
          git config --local user.email "action@github.com"
          git config --local user.name "GitHub Action"
          git add README.md
          git diff --staged --quiet || git commit -m "🕐 Auto update time: $(date)"
          git push
<!--
**huazhounb/huazhounb** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
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
