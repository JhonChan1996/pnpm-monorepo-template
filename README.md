# 开始

## 全局依赖

```
npm install pnpm commitizen -g
```

## 下载依赖

```
pnpm install
```

# 子模块相关操作

## 添加子模块

```
git submodule add <url> <repo_name>
```

## 首次拉取子模块

```
git submodule update --init --recursive
```

## 更新子模块

```
更新项目内子模块到最新版本
git submodule update --remote
更新子模块为远程项目的最新版本
git submodule update --remote
更新某一个子模块为远程项目的最新版本
git submodule update --remote apps/monorepo-apps-demo1
```

更新完成之后，主模块需要执行 git submodule update

## 删除子模块

> rm -rf 子模块目录

```
git rm --cached moduleName
rm -rf moduleName
```

> 删除 .gitmodules 文件中相关子模块的信息

```
[submodule "moduleName"]
        path = moduleName
        url = https://github.com/xxx/moduleName.git
```

> 删除 .git/config 中相关子模块信息

```
[submodule "moduleName"]
        url = https://github.com/xxx/moduleName.git
        active = true
```

> 删除 .git 文件夹中的相关子模块文件

```
rm -rf .git/modules/GWToolkit
```

# 公共模块更新

1. 切换到需要更新的模块
2. 手动修改 `package.json` 中的 `version` 字段
3. 进入需要更新的模块目录
4. pnpm up "@packages/components" | pnpm up "@packages/\*"

## commit 提交

```
cz | git cz
```

# 问题

## 子模块 git status 遇到 HEAD detached at xxx

1. git branch temp xxx
2. git checkout main
3. git merge temp
4. git branch -d temp
5. git push
