---
title: 小狼毫 3 分钟入门及进阶指南
date: 2020-11-27
category:
  - 工具
tag:
  - 小狼毫
  - 输入法
order: -32
---

常年使用搜狗输入法，备份时发现搜狗词库高达 27 万条，其中 99% 的内容是垃圾词条，即使偶尔输入过一次的内容也被输入法记录。更可怕的是，这次词库无法从云端删除，只要你输入过一次，搜狗就永远记住了。

这哪里是输入法，根本是个**键盘记录器**。

之后尝试了各种输入法，百度、讯飞、手心等依旧是键盘记录器，影子输入法开源但不稳定，谷歌拼音停止更新，微软拼音词库收录慢且难以转移，只有小狼毫开源稳定又能多设备同步词库。

下载小狼毫：[官方渠道](https://github.com/rime/weasel/releases/download/0.14.3/weasel-0.14.3.0-installer.exe)，[国内搬运](https://wwi.lanzoui.com/iDyF4pdzmni)。

## 基础设置

安装小狼毫时，不要修改用户文件夹位置，否则后续输入法定制容易出错。安装好后，右键任务栏小狼毫图标，依次点击「输入法设定」- 勾选输入法（推荐「朙月拼音·简化字」）- 选择皮肤，然后正常使用小狼毫输入法了。^[[30 分钟搞定 自由输入法 RIME 简明配置指南](https://www.jianshu.com/p/296bba666604)]^[[Rime 输入法—鼠须管 (Squirrel) 词库添加及配置](https://www.jianshu.com/p/cffc0ea094a7)]

小狼毫不推荐使用 [四叶草](https://github.com/fkxxyz/rime-cloverpinyin) 之类的集成方案，建议参考 [Squirrel 鼠须管配置](https://github.com/ssnhd/rime) 和 [小狼毫 [rime_win][眀月拼音] 简单配置方法](https://blog.csdn.net/qq_42204675/article/details/86422450) 以「朙月拼音·简化字」为基础定制你自己的输入法，最大限度提升输入法效率。小狼毫的魅力正在于可自定义，让输入法按你的想法输出，定制流程参考下面的进阶指南。

## 扩充词库

扩充词库包含英文联想、网络流行语、成语、俗语等，能提升输出效率。热门词库有 [BetterRime 词库](https://github.com/Chernfalin/better-rime-dict)、[SuperRime 拓展词库](https://github.com/Chernfalin/SuperRimeDict)、[自定义短语](https://gist.github.com/lotem/5440677) 和 [Rime 擴充詞庫](https://github.com/rime-aca/dictionaries)。

从容量上来说，SuperRime 词库 > BetterRime 词库 > Rime 擴充詞庫，但词库越大错误收录也越多，建议按实际需求选择词库。

词库解压后，修改 `luna_pinyin.extended.dict.yaml`，选择启用词库范围。`mysymbols.yaml` 对全角和半角符号都做了优化，有其他需求可以自行修改。

## 双拼方案

为提高效率，[小狼毫官方配置库](https://github.com/rime/rime-double-pinyin) 收录了自然码双拼、智能 ABC 双拼、小鹤双拼、MSPY 双拼、拼音加加双拼，我使用的是小鹤双拼，配置流程如下：

1. 将官方配置库中的 [double_pinyin_flypy.schema.yaml](https://github.com/rime/rime-double-pinyin/blob/master/double_pinyin_flypy.schema.yaml) 下载到用户文件夹。
2. 设置好后，右键点击任务栏小狼毫图标，选「输入法设定」，只勾选一个「小鹤双拼」。
3. 默认方案为繁体，可使用按键 F5 (部分版本是 F4)，将配置默认为简体。
4. 双拼只不会显示当前输出字母，可按下方配置修改 [使用双拼时如何同时显示按下的键以及双拼对应的拼音](https://github.com/rime/rime-double-pinyin/issues/6#issuecomment-754367706)。

如果想在双拼中实现自定义短语，可参考 [小狼毫自定义短语-Rime-双拼](https://blog.csdn.net/neninee/article/details/83692270)。如果设定后，无法使用简体输入，将 `double_pinyin_flypy.schema.yaml` 中的 filters 模块转移到 translators 模块上方。

## 进阶指南

小狼毫进阶前，需进入小狼毫默认的用户文档位置，新建 yaml 文档来存储输入法设置修改。如果使用「朙月拼音·简化字」输入法方案，则新建 「luna_pinyin_simp.custom.yaml」。`%APPDATA%\Rime` 是小狼毫默认的用户文档位置。如果安装时修改过用户文档位置，右键点击任务栏小狼毫图标，选「用户文件夹」，即会进入用户文档。^[[小狼毫 RIME 输入法配置](https://www.dazhuanlan.com/2019/10/06/5d995d43e4432/)]

Rime 的官方文档非常详细，涵盖几乎所有的进阶需求，比如 [定制指南](https://github.com/rime/home/wiki/CustomizationGuide)、[文件配置说明](https://github.com/rime/home/wiki/RimeWithSchemata#rime-%E4%B8%AD%E7%9A%84%E6%95%B8%E6%93%9A%E6%96%87%E4%BB%B6%E5%88%86%E4%BD%88%E5%8F%8A%E4%BD%9C%E7%94%A8)、[emoji 集成](https://github.com/rime/rime-emoji) 和 [模糊音设置](https://github.com/rime/home/wiki/CustomizationGuide#%E6%A8%A1%E7%B3%8A%E9%9F%B3)。

如果要多设备 [同步用户资料](https://github.com/rime/home/wiki/UserGuide#%E5%90%8C%E6%AD%A5%E7%94%A8%E6%88%B6%E8%B3%87%E6%96%99)，则打开用户文件夹中的 `installation.yaml`，将其中的设备名称 `installation_id` 从长字符串修改为方便识别的名称，并在 `installation.yaml` 文本最下方添加用户资料同步位置 `sync_dir: 'D:\Sync\RIME'`。

小狼毫主版本长年未更新，下载 rime 输入法的核心库 [librime](https://github.com/rime/librime/releases) 替换小狼毫目录中的 rime.dll 即可完成输入法更新。

注意：

- 同步文件夹路径中不能出现中文。
- 打字习惯会保存在 `<词典名>.userdb.txt`、 `<词典名>.userdb.kct.snapshot`，还原时手工导入词典。

## 常见问题

### 开机后不能输出中文

有时开机后，不能正常输出中文，这是由于 `WeaselServer.exe` 未正常启动的原因。

此时，我们只需打开程序文件夹中的 `WeaselServer.exe` 即可解决问题，该程序默认位置为 `C:\Program Files (x86)\Rime\weasel-0.14.3\WeaselServer.exe`。不要直接将 `WeaselServer.exe` 放入开启启动程序，会导致程序报错。

不愿手动启动 `WeaselServer.exe` 的话，可以使用 [WeaselServerAutostart](https://github.com/rockbenben/rime-WeaselServer) 脚本工具来启动。首先把脚本放置于小狼毫「程序文件夹」内，然后将脚本的快捷方式移动至开机启动目录 `%AppData%\Microsoft\Windows\Start Menu\Programs\Startup`。当开机时，检测到小狼毫未正常启动，脚本会自动启动对应程序。WeaselServerAutostart 脚本国内下载：<https://wwx.lanzoux.com/if3znkka01g>。

### 输入法报错

将用户文件夹置为同步文件夹后，提示「有错误，请查看日志%TEMP%\rime.weasel.\*.INFO」。这是由于用户文件夹置为同步文件夹后导致的进程冲突。日志中有提示「另一个程序正在使用此文件，进程无法访问」。

遇到报错后，关闭任务管理器中的 `WeaselServer.exe` 进程，然后重新执行小狼毫算法服务。

### 输入法候选框闪烁

中文输入法的候选框闪烁，无法显示候选词。

排除键盘硬件问题，拔除或更换键盘，确认问题是否复现。Word 2016 下候选框闪烁参考 [issue 228](https://github.com/rime/weasel/issues/228)。

### 删除错误「上屏」的词

有时打错几次的字总放在预选词的前排，干扰输入法习惯。

把选字光标移到错词上，再按下 Shift+Delete 或 Control+Delete，就能删除错误「上屏」的词。

### 符号直接上屏

小狼毫给字符都提供了多个候选，比如 / 默认有 `"、", "/", "／", "÷"` 四个候选词。如果你想按 / 键直接输出「、」，则按下方代码修改 luna_pinyin.schema.yaml 中的 punctuator 区块。^[[一例、定製標點符號](https://github.com/rime/home/wiki/CustomizationGuide#%E4%B8%80%E4%BE%8B%E5%AE%9A%E8%A3%BD%E6%A8%99%E9%BB%9E%E7%AC%A6%E8%99%9F)]

```yaml
punctuator:
  import_preset: default
  full_shape:
    "/" : "、"
  half_shape:
    "/" : "、"
```

### 指定程序中默认输入法

如果想在特定程序中默认使用英文输入法，在 `.\weasel.custom.yaml` 中加入下列代码即可。

```yaml
patch:
  app_options/windowsterminal.exe: # 程序名字全用小寫字母
    ascii_mode: true
  app_options/powershell.exe:
    ascii_mode: true
  app_options/code.exe:
    ascii_mode: true
  app_options/putty.exe:
    ascii_mode: true
  app_options/listary.exe:
    ascii_mode: true
```

### 不能输出 emoji

即使按按教程设置了 emoji，但还是无法显示，暂时没解决办法。

官方文档、三种集成词库我都试过了，同样无法显示。特殊字符可使用 SuperRime 词库的 symbol 输出。

### 无法触发词库的特殊符号

SuperRime 词库自带的标点及特殊表情设置有问题，需在输入法设置文件夹 `luna_pinyin_simp.custom.yaml` 中植入触发标点及特殊表情的代码。

```yaml
patch:
  "punctuator/import_preset": mysymbols
  "recognizer/patterns/punct": "^/([a-z]+|[0-9])$"
```
