## 前言

我的 Rime 配置仓库，顺便记录一些遇到的问题和解决方案。

TODO: 2023-09-19 麻了！💢 Rime 配置的 16 进制配色和正常的 16 进制配色颜色表对不上啊，想自定义颜色都不好弄，设置出来更像是互补色。只有在调出来的才是对的：[Rime 西米](https://fxliang.github.io/RimeSeeMe/)。

✅ 2023-12-01 Rime 打不出来 “划词” 这个词语，“划”和“词”单独都能打出来，划词就不行，还得自己去配置单独加一下这个，离谱。

## Rime 默认词库的联想词总是怪怪的？这个拼音方案真的无敌！

先上一波链接，这里又三个地址，分别是 Github 源码、文档、安装工具：

- [GitHub - rime-ice](https://github.com/iDvel/rime-ice)
- [Rime 配置：雾凇拼音 - Dvel's Blog](https://dvel.me/posts/rime-ice/)
- [Rime plum](https://github.com/rime/plum)

## Mac 获取指定 App 的 app_options

把 `Raycast.app` 更换为其他你想要获取的 App 应用名称即可。

```shell
grep -A 1 "CFBundleIdentifier" /Applications/Raycast.app/Contents/Info.plist
```

如图：

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/grep%20%E8%8E%B7%E5%8F%96%20Mac%20%E5%BA%94%E7%94%A8%20app_options.png)

图中框选的 `com.raycast.macos` 就是你想要的值

## 自定义皮肤主题

感觉雾凇拼音默认的皮肤有点差强人意，所以自己改了一下，先看效果！不满意也可以基于我的皮肤设置自己爆改奥 ⚡

> 短词

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Rime%20%E8%87%AA%E5%AE%9A%E4%B9%89%E7%9A%AE%E8%82%A4%E6%95%88%E6%9E%9C%E7%9F%AD%E8%AF%8D.png)

> 长词

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Rime%20%E8%87%AA%E5%AE%9A%E4%B9%89%E7%9A%AE%E8%82%A4%E6%95%88%E6%9E%9C%E9%95%BF%E8%AF%8D.png)

```yaml
style:
  # 选择皮肤，亮色与暗色主题
  color_scheme: google_custom

# 皮肤列表
preset_color_schemes:
  google_custom:
    name: "小小石爆改"
    horizontal: true                          # true横排，false竖排
    back_color: 0xFFFFFF                      # 候选条背景色
    border_height: 0                          # 窗口上下高度，大于圆角半径才生效
    border_width: 8                           # 窗口左右宽度，大于圆角半径才生效
    candidate_format: "%c %@ "                # 用 1/6 em 空格 U+2005 来控制编号 %c 和候选词 %@ 前后的空间
    comment_text_color: 0x999999              # 拼音等提示文字颜色
    corner_radius: 6                          # 窗口圆角
    hilited_corner_radius: 5                  # 高亮圆角
    font_face: PingFangSC                     # 候选词字体
    font_point: 18                            # 候选字大小
    hilited_candidate_back_color: 0xF5803B   # 第一候选项背景色
    hilited_candidate_text_color: 0xFFFFFF    # 第一候选项文字颜色
    label_font_point: 14                      # 候选编号大小
    text_color: 0x424242                      # 拼音行文字颜色
    inline_preedit: true                      # 拼音位于： 候选框 false | 行内 true
```

## 给用 Vim 的应用加上 ESC 自动切换英文功能（留下 Rime 主要原因！）

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Rime%20%E8%AE%BE%E7%BD%AE%20Vim%20%E6%A8%A1%E5%BC%8F.png)

## VS Code 快捷键冲突问题

参考文档：[定制呼出方案的快捷键](https://github.com/rime/home/wiki/CustomizationGuide#%E4%B8%80%E4%BE%8B%E5%AE%9A%E8%A3%BD%E5%96%9A%E5%87%BA%E6%96%B9%E6%A1%88%E9%81%B8%E5%96%AE%E7%9A%84%E5%BF%AB%E6%8D%B7%E9%8D%B5)

主要是解决 Control + \` 新建终端快捷键冲突，把途中圈起来的代码注释即可。

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Rime%20%E6%B3%A8%E9%87%8A%E6%96%B9%E6%A1%88%E9%80%89%E6%8B%A9%E5%BF%AB%E6%8D%B7%E9%94%AE.png)

## iCloud 同步（旧的不推荐了）

2023-12-07 如果你会 Git，那我更推荐推送到 Git 远程仓库方式进行同步，能够清晰的看到历史提交内容的修改记录。

参考文档：[同步至 iCloud](https://github.com/ssnhd/rime#%E5%90%8C%E6%AD%A5%E8%87%B3-icloud)

1. 打开 Rime 的配置目录，找到 `installation.yaml` 文件；
2. 添加参数 `sync_dir`，把 `feng` 替换成你自己的管理员名称即可；
3. 更改参数 `installation_id` 这是后续同步的目录名称；
4. 点击菜单栏【ㄓ】-【同步用户数据】；
5. 打开 iCloud 查看是否同步成功。

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Rime-%E5%90%8C%E6%AD%A5%20iCloud.png)
