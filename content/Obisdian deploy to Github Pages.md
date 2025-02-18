Quartz 官網：
https://quartz.jzhao.xyz/
教學文：
https://notes.nicolevanderhoeven.com/How+to+publish+Obsidian+notes+with+Quartz+on+GitHub+Pages


有三個元件：
- [Obsidian](https://notes.nicolevanderhoeven.com/obsidian-playbook/Using+Obsidian/01+First+steps+with+Obsidian/Obsidian) as an interface to create and edit notes in [Markdown](https://notes.nicolevanderhoeven.com/obsidian-playbook/Using+Obsidian/02+Making+Notes+in+Obsidian/Markdown)
- [Quartz](https://notes.nicolevanderhoeven.com/Quartz) as a [Static site generator](https://notes.nicolevanderhoeven.com/Static+site+generator) to turn the Markdown into HTML
- [GitHub Pages](https://notes.nicolevanderhoeven.com/GitHub+Pages) as a hosting provider


## 🪴 Get Started

Quartz requires **at least [Node](https://nodejs.org/) v20** and `npm` v9.3.1 to function correctly.

Then, in your terminal of choice, enter the following commands line by line:
```shell nums
git clone https://github.com/jackyzha0/quartz.git
cd quartz
npm i
npx quartz create
```
(git clone後面可以加上 -f YOUR_NAME，然後改成cd YOUR_NAME)

在 /quartz 底下 ，可以看到已建立git
```shell nums
% git remote -v
origin https://github.com/jackyzha0/quartz.git (fetch)
origin https://github.com/jackyzha0/quartz.git (push)
```


## [[新增Obsidian頁面]]

## [[同步到Github]]

