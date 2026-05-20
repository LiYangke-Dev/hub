# **《GitHub 个人开发体系使用说明书》**



------

### 📘 个人开发体系使用说明书

#### 体系核心逻辑

这套体系将你的代码和知识分为了四个维度：

- **hub**：你的门面与知识库（对外展示 + 沉淀）。
- **lab**：你的草稿纸与实验室（试错 + 学习）。
- **template**：你的军火库（提效工具）。
- **prj-**：你的战利品（正式项目）。

------

#### 场景一：新电脑初始化（仅做一次）

当你拿到一台新电脑，或者重装系统后，按照以下步骤操作：

1. **安装环境**：安装 Git, VS Code, Keil, Python 等基础软件。

2. **配置 Git**：

   ```bash
   git config --global user.name "你的名字"
   git config --global user.email "你的邮箱"
   ```

3. **拉取 hub 仓库**：

   ```bash
   git clone https://github.com/你的用户名/hub.git
   ```

4. **查阅配置清单**：

   - 打开 `hub/docs/environment/vscode-setup.md`，按照里面的清单安装 VS Code 插件。
   - 打开 `hub/docs/resources/useful-websites.md`，找回你常用的工具网站。

------

#### 场景二：学习新技术 / 做小实验（日常高频）

当你想要学习一个新功能（比如 STM32 的定时器），或者测试一段新代码时：

1. **进入 lab 仓库**：

   ```bash
   cd lab
   git pull  # 同步最新进度
   ```

2. **创建实验文件夹**：

   - 路径：`lab/embedded/stm32/2026-05-tim-pwm/`
   - 动作：在这里写代码、炸板子、调试。

3. **记录踩坑笔记**：

   - 如果遇到了报错，随手在 `lab/notes/` 下新建一个 `.md` 记录解决方法。

4. **实验结束**：

   - 如果实验成功，完善该文件夹下的 `README.md`（使用实验记录模板）。

   - 提交代码：

     ```bash
     git add .
     git commit -m "完成定时器PWM输出实验"
     git push
     ```

------

#### 场景三：开启一个正式项目（大工程）

当你决定要做一个完整的作品（比如智能小车）参加比赛或放入简历时：

1. **复制模板**：

   - 找到 `template` 仓库中的 `stm32-hal-template`。
   - 复制整个文件夹，重命名为 `prj-smartcar`。

2. **初始化仓库**：

   - 在 GitHub 上新建一个名为 `prj-smartcar` 的空仓库。

   - 在本地 `prj-smartcar` 文件夹中执行：

     ```bash
     git init
     git remote add origin https://github.com/你的用户名/prj-smartcar.git
     git add .
     git commit -m "项目初始化"
     git push -u origin main
     ```

3. **完善项目文档**：

   - 打开 `prj-smartcar/README.md`，按照模板填入项目简介、功能列表。
   - 在 `assets/` 文件夹放入小车照片。

4. **开发过程**：

   - 所有的代码迭代都在这个仓库进行。
   - 遇到的技术难题，解决后总结成文章，发布到 `hub/docs/tutorials/` 中（把项目经验转化为知识资产）。

------

#### 场景四：知识沉淀与维护（每周/每月）

不要让仓库变成死数据，要定期维护：

1. **整理 lab**：
   - 查看 `lab` 中那些已经验证成功的实验。
   - 思考：这个实验是否可以提炼成一个通用的 `template`？如果是，复制到 `template` 仓库。
2. **更新 hub**：
   - 如果你学会了新技能（比如 Docker），更新 `hub/README.md` 的技术栈列表。
   - 如果你发现了好用的新工具，更新 `hub/docs/resources/`。
3. **归档旧项目**：
   - 如果某个 `prj-` 项目已经彻底过时且不再维护，将其移动到 `archive` 仓库，保持主列表清爽。

------

#### 附录：文件夹速查表

| 当我想...           | 我去哪个仓库？ | 具体操作                 |
| ------------------- | -------------- | ------------------------ |
| **改个人简介**      | `hub`          | 编辑 `README.md`         |
| **查 VS Code 插件** | `hub`          | 查看 `docs/environment/` |
| **测试新代码**      | `lab`          | 新建日期文件夹，随便折腾 |
| **查以前的报错**    | `lab`          | 搜索 `notes/` 里的记录   |
| **建新项目**        | `template`     | 复制对应的骨架文件夹     |
| **做比赛项目**      | `prj-xxx`      | 严肃开发，写好文档       |
| **清理旧代码**      | `archive`      | 把不用的项目移进去       |

------

**🚀 现在的行动建议：**
以后每当迷茫“这个文件该放哪”的时候，看一眼这份说明书即可。