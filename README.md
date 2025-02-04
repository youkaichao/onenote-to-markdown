# OneNote导出成Markdown文件的脚本

## 步骤

### 安装Pandoc

在 https://pandoc.org/ 网站下载安装Pandoc软件，默认会加入到Path环境变量中。打开cmd并输入 pandoc ，如果没提示找不到命令，就是成功了。

### 准备个Python3.8+的环境


1. 安装依赖.

```bash
pip install -r requirements.txt
```

2. 打开OneNote软件（注意，需要是OneNote 2016，不能是OneNote For Win10之类的版本，详情查看 https://support.microsoft.com/zh-cn/office/onenote-%E7%89%88%E6%9C%AC%E6%9C%89%E4%BD%95%E5%8C%BA%E5%88%AB-a624e692-b78b-4c09-b07f-46181958118f ）

3. 运行代码. （代码里有个 ASSETS_DIR 变量，是图片存放路径。如果你在obsidian里有相关设置，可以修改这个变量）

```bash
python convert.py
```

4. 你的笔记应该转化成了markdown文件并存在 `~/Desktop/OneNoteExport`. 建议用[obsidian](https://obsidian.md)管理markdown笔记！

# 致谢

这部分代码来自 https://github.com/pagekeytech/onenote-to-markdown 。喜欢用powershell脚本的朋友可以使用仓库中的 convert3.ps1 脚本。

# 已知问题

部分OneNote笔记的笔记名包含特殊字符，可能转换失败。因为目标格式是markdown并且以文件、文件夹格式存储，必然受到操作系统对文件名的限制。对于这种情况，我的建议是以后不要在标题里用特殊字符。
