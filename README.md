# techblog

系统 [Hexo](https://hexo.io/zh-cn/docs/) 
主题 [Next](http://theme-next.iissnan.com)

## 安装

```
git clone https://github.com/NJU-itxia/techblog.git
npm install
```

## 发布文章

```
hexo new your-article # 在 /source/_posts 下编辑
hexo deploy # 会把 /public 的内容 push 到 gh-pages 分支
```

别忘了 commit 主分支，并 push
```
git add --all
git commit -m "your-commit"
git push origin master
```
