# 说明

本项目是基于`hexo`的快速生成静态博客页面的工具。

有两个分支：

- source

  - 存放源代码
  - 创建，编辑文章

- main
  - 存放最终生成的文件

## 环境配置

### 一、如需要在本地手动构建并部署博客站点，必须按照如下步骤安装环境

需要在 `develop` 分支。

- 1、安装 Node.js
- 2、安装 `Hexo`

  `npm install hexo -g`

- 3、安装本地依赖

  `npm install`

#### 常用命令

```shell
hexo s  # 本地预览博客
hexo g  # 生成博客网页文件
hexo d  # 部署到github
```

### 二、自动构建并部署博客站点（无需安装上述环境）

#### a、配置 personal_token

##### 第一步，生成 token

[地址](https://github.com/settings/tokens)

- 点击 `Generate new token` 按钮
- Note 随便填
- 下方勾选 `repo` 即可
- 点击最下方 `Generage` 按钮
- 复制生成的 token ⚠️：一定要先复制，页面关闭就看不见了。

##### 第二步，将 token 添加到项目的 secrets 中

在本项目的 git 仓库 `Setting > Secrets`

- 点击 New repository secret
- name 填写 `ACCESS_TOKEN`(和.github/workflows/deploy.yml 中一致)
- value 填写第一步中生成的 token

#### b、配置 deploy_key

##### 第一步 生成 SSH

[步骤](https://blog.csdn.net/qq_40741855/article/details/83338596)

##### 第二步

在本项目的 git 仓库 `Setting > Deploy keys`

- 点击 Add deploy key
- Title 填写 `GIT_PAGE_TOKEN`(和.github/workflows/deploy.yml 中一致)
- 复制第一步中生成的`id_rsa.pub`文件内容，粘贴到 key 栏目中

source 分支 push 代码，会触发 github 的 actions 自动构建静态博客站点并推送到 `main` 分支

## 写文章

添加文章需要在 `develop` 分支上，不能在 main 分支

## 方式一：到`\source\_posts`目录新建 `md` 文件，编辑文章内容即可

## 方式二：命令行创建文章（需要安装环境配置第 2 点）

命令行输入：`hexo new post "article title"`

即可在`\source\_posts`目录下生成一篇文章
