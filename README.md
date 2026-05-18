# astrbot_plugin_sbhtest

这是一个基于 `shoubanhua` 插件做少量功能增强的 AstrBot 插件测试版。

本插件并不是全新原创插件，只是在原插件基础上增加了几个使用便利功能，核心绘图能力、主要逻辑和基础功能来自原版 shoubanhua 插件。

## 原插件信息

- 原作者：帅气逼人
- 原作者主页：[https://github.com/shskjw](https://github.com/shskjw)
- 原插件仓库：[shskjw/astrbot_plugin_shoubanhua](https://github.com/shskjw/astrbot_plugin_shoubanhua)

感谢原作者提供的 shoubanhua 插件。

## 本版本新增功能

### API 组合管理

可以保存多个常用 API 中转站配置，并通过指令快速切换，不用每次手动改 API 地址和 Key。

支持的指令：

| 指令 | 说明 |
| --- | --- |
| `#API组合列表` | 查看已保存的 API 组合 |
| `#API组合当前` | 查看当前正在使用的 API 组合 |
| `#API组合添加 <名称> <generic\|gemini_official> <API地址> <Key1> [Key2...]` | 添加或更新一个 API 组合 |
| `#API组合切换 <名称或序号>` | 切换到指定 API 组合 |
| `#API组合删除 <名称或序号>` | 删除指定 API 组合 |

说明：

- `#API组合列表` 会显示当前模型名。
- Key 在列表中会自动遮罩，只保留开头一小段，避免发到群里泄露完整 Key。
- 切换 API 组合不会改动现有的模型切换逻辑。

示例：

```text
#API组合添加 blt generic https://api.example.com sk-xxxxxx
#API组合列表
#API组合切换 blt
```

### 重发最后一次生成的图

如果图片刚才生成过，但聊天里想再发一次，可以使用重发指令。

支持的指令：

| 指令 | 说明 |
| --- | --- |
| `#重发最后一张图` | 重发当前会话最近一次成功生成的图片 |
| `#重发图片` | 同上 |
| `#重发最后图片` | 同上 |
| `#再发一次` | 同上 |
| `#重发上一张图` | 同上 |

说明：

- 图片缓存按当前群聊/私聊会话区分。
- 不会把其他群或其他私聊里的图片串过来。
- 如果当前会话还没有可重发的生成图，会提示暂无可重发图片。

## 安装

将插件目录或打包后的 zip 上传到 AstrBot 插件管理页面安装即可。

插件目录名和插件名为：

```text
astrbot_plugin_sbhtest
```

## 备注

本仓库仅用于保存基于 shoubanhua 插件的小改版，主要新增 API 组合管理和重发最后生成图功能。原插件的完整功能说明、配置说明和使用方式请参考原仓库：

[shskjw/astrbot_plugin_shoubanhua](https://github.com/shskjw/astrbot_plugin_shoubanhua)
