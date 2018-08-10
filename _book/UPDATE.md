# GitBook 自动化部署 GitHub Page 配置方法与流程

## 实现思路

- GitHub 新建分支 `gh-pages`
- 将 `gitbook build` 后生成的 `_book` 静态文件 `push` 到 `gh-pages` 上
- 将 `gh-pages` 分支设置为 GitHub Page 源
- 通过 `gitbook.sh` 脚本同时更新 `master` 和 `gh-pages`

## 配置方法

初始化配置方法如下，或直接拉取 `gh-pages` 分支

### 新建 `gh-pages` 分支

```sh
git checkout --orphan gh-pages
```

### 删除不需要的文件

切换到 `gh-pages` 分支后，我们需要将 `_books` 目录之外的文件清理掉

```sh
git rm --cached -r .
git clean -df
rm -rf node_modules
```

### 添加 `.gitignore` 文件

```sh
*~
_book
.DS_Store
```

### 复制 `_book` 文件夹内的所有文件到 `gh-pages` 分支根目录

```sh
cp -r _book/* .
```

### 推送 `gh-pages` 分支到远程仓库

```sh
git add .
git commit -m '+add gh-pages branch'
git push -u origin gh-pages
```

## 使用脚本自动化更新

生成静态文件

```
gitbook build
```

同时更新 `master` 和 `gh-pages`

```sh
sh gitbook.sh '更新说明'
```

脚本内容

```sh
git checkout master
git add .
git commit -m $1
git push -u origin master
git checkout gh-pages
cp -r _book/* .
git add .
git commit -m $1
git push -u origin gh-pages
git checkout master
```