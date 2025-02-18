
在Github創立新的repository，複製SSH ``REMOTE-URL``

![[2025-02-17 11.12.46.png]]

In your terminal of choice, navigate to the root of your Quartz folder. Then, run the following commands, replacing `REMOTE-URL` with the URL you just copied from the previous step.
```shell nums
# list all the repositories that are tracked
git remote -v
 
# if the origin doesn't match your own repository, set your repository as the origin
git remote set-url origin REMOTE-URL
 
# if you don't have upstream as a remote, add it so updates work
git remote add upstream https://github.com/jackyzha0/quartz.git
```

[[Obisdian deploy to Github Pages]]