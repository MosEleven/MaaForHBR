<!-- markdownlint-disable MD033 MD041 -->
<p align="center">
  <img alt="LOGO" src="https://cdn.jsdelivr.net/gh/MaaAssistantArknights/design@main/logo/maa-logo_512x512.png" width="256" height="256" />
</p>

## 本项目基于MaaFramework制作

### 已实现功能

- 启动、唤醒游戏

- 活动棱镜战

- 竞技场挂机

  - 目前只提供高级2挂机选项

- maa自动战斗

  1. 需要提前打一遍关卡，保证操作能100%复刻

  2. 打关卡时，按照如下规则把“操作”记录下来

     - 角色从左到右编号为1-6，技能从上到下编号为abc，“开始行动”为7，OD条为8

     - “操作“有如下几种（实际上就是你的点击顺序）

       - 换位：例如数字“15”表示1号位和5号位换位，数字“62”表示6号位和2号位换位
       - 释放技能：例如“2c”表示2号位放c技能，“3a”表示3号位放a技能
       - 释放技能给另一个角色：例如“1a3”表示1号位放a技能目标是3号角色
       - 单击：例如“7”表示点击开始行动，“8”表示释放OD
       - 注意，实际记录数字时不需要加双引号

     - 每个“操作”之间用英文逗号隔开，每轮操作结束加一个英文分号

     - 示例：7;7;7;14,1a4,3a4,7;34,1a3,26,2a,3b,7;15,1a,7;41,1b,2a,7,8;1a3,25,2a3,3b,7;

       上面是一个操作记录，前3轮都只点了一下开始行动就没了。第四轮执行的操作分别为1号和4号换位，1号放1技能给4号，3号放1技能给4号，点击开始行动。倒数第二轮是点了开始行动，再点了OD才结束的。

  3. 把记录下来的操作，复制进“fight_strategy.txt”文件中，如果里面有内容就先删干净，只保留你最新的记录，保存文件。

  4. 双击“JsonCreator.exe”，会生成相应的配置文件。

- 暂留

### 未实现功能

- 图形化界面
- 除活动棱镜战和竞技场外的其他作战，如废域迷宫，宝珠光球……
- 自动去商店卖货
- 任务领取
- 体力检测
- 消耗体力石
- 重复作战、
- 目前只能保存一套作战逻辑，后续可以扩展给每个队伍保存一套



------

以下是MaaFramework readme文件

------
<div align="center">

# MaaPracticeBoilerplate

</div>

本仓库为 [MaaFramework](https://github.com/MaaXYZ/MaaFramework) 所提供的项目模板，开发者可基于此模板直接创建自己的 MaaXXX 项目。

> **MaaFramework** 是基于图像识别技术、运用 [MAA](https://github.com/MaaAssistantArknights/MaaAssistantArknights) 开发经验去芜存菁、完全重写的新一代自动化黑盒测试框架。
> 低代码的同时仍拥有高扩展性，旨在打造一款丰富、领先、且实用的开源库，助力开发者轻松编写出更好的黑盒测试程序，并推广普及。

## 即刻开始

- [⭐ 开发思路](https://github.com/MaaXYZ/MaaFramework/blob/main/docs/zh_cn/0.1-%E5%BC%80%E5%8F%91%E6%80%9D%E8%B7%AF.md)
- [📄 资源准备](https://github.com/MaaXYZ/MaaFramework/blob/main/docs/zh_cn/1.1-%E5%BF%AB%E9%80%9F%E5%BC%80%E5%A7%8B.md)
- [🎞️ 视频教程](https://www.bilibili.com/video/BV1yr421E7MW)

## 如何开发

0. 使用右上角 `Use this template` - `Create a new repository` 来基于本模板创建您自己的项目。

1. 完整克隆本项目及子项目（地址请修改为您基于本模板创建的新项目地址）。

    ```bash
    git clone --recursive https://github.com/MaaXYZ/MaaPracticeBoilerplate.git
    ```

    **请注意，一定要完整克隆子项目，不要漏了 `--recursive`，也不要下载 zip 包！** 这步未正确操作会导致所有 OCR（文字识别）失败！

2. 下载 MaaFramework 的 [Release 包](https://github.com/MaaXYZ/MaaFramework/releases)，解压到 `deps` 文件夹中。

3. 配置资源文件。

    ```bash
    python ./configure.py
    ```

4. 按需求修改 `assets` 中的资源文件，请参考 MaaFramework 相关文档。

    - 可使用 [MaaDebugger](https://github.com/MaaXYZ/MaaDebugger) 进行调试；
    - 也可以在本地安装后测试：

        1. 执行安装脚本

            ```bash
            python ./install.py
            ```

        2. 运行 `install/MaaPiCli.exe`

5. 完成开发工作后，上传您的代码并发布版本。

    ```bash
    # 配置 git 信息（仅第一次需要，后续不用再配置）
    git config user.name "您的 GitHub 昵称"
    git config user.email "您的 GitHub 邮箱"
    
    # 提交修改
    git add .
    git commit -m "XX 新功能"
    git push origin HEAD -u
    ```

6. 发布您的版本

    需要先修改仓库设置 `Settings` - `Actions` - `General` - `Read and write permissions` - `Save`

    ```bash
    # CI 检测到 tag 会自动进行发版
    git tag v1.0.0
    git push origin v1.0.0
    ```

## 生态共建

MAA 正计划建设为一类项目，而非舟的单一软件。

若您的项目依赖于 MaaFramework，我们欢迎您将它命名为 MaaXXX, MXA, MAX 等等。当然，这是许可而不是限制，您也可以自由选择其他与 MAA 无关的名字，完全取决于您自己的想法！

同时，我们也非常欢迎您提出 PR，在 [最佳实践列表](https://github.com/MaaXYZ/MaaFramework#%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5) 中添加上您的项目！

## FAQ

### 1. 我是第一次使用 Python，在命令行输入 `python ./configure.py` 或 `python -m pip install MaaFW` 之后没有反应？没有报错，也没有提示成功，什么都没有

Win10 或者 Win11 系统自带了一份 "Python"，但它其实只是一个安装器，是没法用的。  
你需要做的是关闭它或者删除它的环境变量，然后自己去 Python 官网下载并安装一份 Python。  
[参考方法](https://www.bilibili.com/read/cv24692025/)

### 2. 我输入 `python ./configure.py` 后报错：`Please clone this repository completely, don’t miss "--recursive", and don’t download the zip package!`

![项目不完整1](https://github.com/user-attachments/assets/e1f697c0-e5b6-4853-8664-a358df7327a8)

**请仔细阅读文档！！！**  
就是你现在正在看的本篇文档，就在上面，“如何开发”里的第一条，都已经用粗体标出来了，再问我要骂人了！

### 3. 使用 MaaDebugger 或 MaaPicli 时弹窗报错，应用程序错误：应用程序无法正常启动

![缺少运行库](https://github.com/user-attachments/assets/942df84b-f47d-4bb5-98b5-ab5d44bc7c2a)

一般是电脑缺少某些运行库，请安装一下 [vc_redist](https://aka.ms/vs/17/release/vc_redist.x64.exe) 。

### 4. 我在这个仓库里提了 Issue 很久没人回复

这里是《项目模板》仓库，它仅仅是一个模板，一般很少会修改，开发者也较少关注。  
在此仓库请仅提问模板相关问题，其他问题最好前往对应的仓库提出，如果有 log，最好也带上它（`debug/maa.log` 文件）

- MaaFW 本身及 MaaPiCli 的问题：[MaaFramework/issues](https://github.com/MaaXYZ/MaaFramework/issues)
- MaaDebugger 的问题：[MaaDebugger/issues](https://github.com/MaaXYZ/MaaDebugger/issues)
- 不知道算是哪里的、其他疑问等：[讨论区](https://github.com/orgs/MaaXYZ/discussions)

### 5. OCR 文字识别一直没有识别结果，报错 "Failed to load det or rec", "ocrer_ is null"

你不但没有仔细阅读文档，还无视了前面步骤的报错。我不想解释了，请再把本文档仔细阅读一遍！

## 鸣谢

本项目由 **[MaaFramework](https://github.com/MaaXYZ/MaaFramework)** 强力驱动！

感谢以下开发者对本项目作出的贡献（下面链接改成你自己的项目地址）:

<a href="https://github.com/MaaXYZ/MaaFramework/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=MaaXYZ/MaaFramework&max=1000" />
</a>
