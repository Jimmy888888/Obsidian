
在Github創立新的repository，複製SSH ``REMOTE-URL``
*因為目前git遠端push只能用SSH key驗證*

![[2025-02-17 11.12.46.png]]


## 1.建立連線

在本地端 /quartz , navigate to the root of your Quartz folder. Then, run the following commands, replacing `REMOTE-URL` with the URL you just copied from the previous step.
```shell nums
# list all the repositories that are tracked
git remote -v
 
# if the origin doesn't match your own repository, set your repository as the origin
git remote set-url origin REMOTE-URL
 
# if you don't have upstream as a remote, add it so updates work(可跳過)
git remote add upstream https://github.com/jackyzha0/quartz.git
```


## 2.添加SSH Key

1 本地生成SSH key，並添加到ssh agent
```shell nums
# gen ssh key
ssh-keygen -t rsa -b 4096 -C "your_email@example.com" -f ~/.ssh/YOUR_NAME
# add the key to ssh agent
ssh-add ~/.ssh/YOUR_NAME
# see the key in ssh agent
ssh-add -L
# if wrong key or many keys in ssh agent, delete it
ssh-add -d ~/.ssh/WROONG_NAME
```

2 把SSH key的public key添加到Github repository



## 3.同步Quartz內容到Github

在 /quartz底下
```shell nums
npx quartz sync --no-pull
```



## 4.[[Host Quartz online]]

## 5.完成以上四步驟就能在Github Pages看到Obsidain筆記

## 上一頁：
[[Export Obisdian]]