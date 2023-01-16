# 开始

## 全局依赖

```
npm install pnpm commitizen -g
```

## 下载依赖

```
pnpm install
```

## 首次拉取子模块

```
git submodule update --init --recursive
```

## 更新子模块

```
git submodule update --remote apps/monorepo-apps-demo1
```

## 更新模块版本

手动修改 `package.json` 中的 `version` 字段

## 更新子模块依赖的公共模块版本

```
pnpm up "@packages/components" | pnpm up "@packages/*"
```

## commit 提交

```
cz | git cz
```
