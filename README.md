# 📬 Cha's Email Template Portfolio

Hi there! I’m Cha — a creative marketing automation specialist passionate about email design, digital storytelling, and all things HTML ✨

- 🔭 I’m currently working on **responsive email templates** using Mailchimp, custom HTML/CSS, and cross-client compatibility techniques  
- 🌱 I’m currently learning **HubSpot** and **Salesforce** (Sales & Marketing Clouds)  
- 🎯 I focus on building mobile-first email designs that are beautiful, high-performing, and easy to reuse across platforms  

---

## 💡 Skills & Tools

<table>
  <tr>
    <td valign="top" width="50%">
      <strong>💻 Development</strong><br/><br/>
      <img src="https://img.shields.io/badge/HTML5-e34f26?logo=html5&logoColor=white" />
      <img src="https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white" />
    </td>
    <td valign="top" width="50%">
      <strong>🧠 Marketing Automation & CRM</strong><br/><br/>
      <img src="https://img.shields.io/badge/Marketo-purple?logo=marketo&logoColor=white" />
      <img src="https://img.shields.io/badge/Mailchimp-ffe01b?logo=mailchimp&logoColor=black" />
      <img src="https://img.shields.io/badge/HubSpot-fd7e14?logo=hubspot&logoColor=white" />
      <img src="https://img.shields.io/badge/Salesforce-00A1E0?logo=salesforce&logoColor=white" />
    </td>
  </tr>
  <tr>
    <td valign="top" width="50%">
      <strong>☁️ SaaS & Collaboration Tools</strong><br/><br/>
      <img src="https://img.shields.io/badge/Google%20Workspace-4285F4?logo=google&logoColor=white" />
      <img src="https://img.shields.io/badge/Google%20Cloud-4285F4?logo=googlecloud&logoColor=white" />
      <img src="https://img.shields.io/badge/Asana-273347?logo=asana&logoColor=f06a6a" />
    </td>
    <td valign="top" width="50%">
      <strong>🎨 Design & Visual Tools</strong><br/><br/>
      <img src="https://img.shields.io/badge/Canva-00C4CC?logo=canva&logoColor=white" />
      <img src="https://img.shields.io/badge/Figma-F24E1E?logo=figma&logoColor=white" />
      <img src="https://img.shields.io/badge/Photoshop-31A8FF?logo=adobephotoshop&logoColor=white" />
      <img src="https://img.shields.io/badge/Illustrator-FF9A00?logo=adobeillustrator&logoColor=white" />
    </td>
  </tr>
</table>


- ✍️ Copywriting using **AIDA Framework** (Attention–Interest–Desire–Action)  
- 📧 Responsive Email Design: HTML tables, inline CSS, VML buttons  
- 📊 A/B Testing & Performance Optimization  
- 📬 Experience with **ESPs** (Email Service Providers)  
- ☁️ Working with **SaaS platforms** and CRM workflows  
- 🧩 Canva for image prep, hero sections, and layout alignment  
- ✅ GDPR-compliant footer structure & unsubscribe best practices  
- 🧠 Currently exploring: **HubSpot Email Builder**, **Salesforce Marketing Cloud**, **HubSpot Workflows**

---
name: GitHub Snake Game

on:
  # Schedule the workflow to run daily at midnight UTC
  schedule:
    - cron: "0 0 * * *"
  # Allow manual triggering of the workflow
  workflow_dispatch:
  # Trigger the workflow on pushes to the main branch
  push:
    branches:
      - main
jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      # Step 1: Checkout the repository
      - name: Checkout Repository
        uses: actions/checkout@v3
      # Step 2: Generate the snake animations
      - name: Generate GitHub Contributions Snake Animations
        uses: Platane/snk@v3
        with:
          # GitHub username to generate the animation for
          github_user_name: ${{ github.repository_owner }}
          # Define the output files and their configurations
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
            dist/ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      # Step 3: Deploy the generated files to the 'output' branch
      - name: Deploy to Output Branch
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
          publish_branch: output
          # Optionally, you can set a custom commit message
          commit_message: "Update snake animation [skip ci]"
📂 **Live Preview Portfolio:** [View my templates](https://ccharoensuk.github.io/ccharoensuk-email-templates-portfolio/)  
📩 Each email includes strategic copy, tested layouts, and real-world use cases
