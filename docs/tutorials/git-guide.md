# Git 命令速查卡片

## 基础配置（新电脑首次执行）

配置全局用户名（与 GitHub 账号一致）：

```bash
git config --global user.name "你的名字"
```

配置全局邮箱（与 GitHub 账号一致）：

```bash
git config --global user.email "你的邮箱"
```

检查所有配置是否成功：

```bash
git config --list
```

## 日常开发高频指令

- 查看当前仓库的状态（看看改了啥）：

```bash
git status
```

- 添加所有修改的文件到暂存区：

```bash
git add .
```

- 只添加指定的某个文件到暂存区：

```bash
git add 文件路径/文件名
```

- 提交到本地仓库（保存存档，引号里写清楚你干了什么）：

```bash
git commit -m "你的提交备注"
```

- 推送到远程 GitHub（上传云端，如果默认分支是 master 则改为 master）：

```bash
git push origin main
```

## 同步与克隆

- 第一次下载项目到本地：

```bash
git clone 远程仓库地址
```

- 更新本地代码（把 GitHub 上别人或自己别的电脑提交的代码拉下来）：

```bash
git pull origin main
```

## “后悔药”系列（撤销操作）

- 文件改乱了，想恢复到上一次提交的状态：

```bash
git checkout -- 文件名
```

- `git add` 加错了，想从暂存区撤回来（但不删除文件修改）：

```bash
git restore --staged 文件名
```

- `git commit` 备注写错了，想修改最后一次提交的备注：

```bash
git commit --amend -m "新的正确备注"
```

## 分支管理

- 查看所有分支：

```bash
git branch
```

- 创建并切换到新分支（比如开发新功能时）：

```bash
git checkout -b 新分支名
```

- 切换回主分支：

```bash
git checkout main
```

- 把开发分支的代码合并到主分支：

```bash
git merge 分支名
```

## 避坑小贴士

1. **提交前必做**：每次 `git push` 之前，先 `git pull` 一下，防止冲突。
2. **忽略文件**：如果不想把 Keil 的编译中间文件（如 `.uvprojx` 生成的 `Objects` 文件夹）传上去，记得在项目根目录新建一个 `.gitignore` 文件。
3. **报错处理**：如果遇到 `Permission denied`，通常是 SSH 密钥没配好，或者需要重新登录 GitHub 账号。