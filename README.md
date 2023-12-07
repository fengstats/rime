## Rime

我的 Rime 配置仓库，顺便记录一些遇到的问题和解决方案。

## 临时

2023-12-01 Rime 打不出来 “划词” 这个词语，“划”和“词”单独都能打出来，划词就不行，还得去配置单独加一下这个，离谱。✅ 已解决：配置

2023-09-19 真服了！💢 Rime 配置的 16 进制配色和正常的 16 进制配色颜色表对不上啊，想自定义颜色都不好弄，设置出来更像是互补色。只有在这里设置的才是准确的：[Rime 西米](https://fxliang.github.io/RimeSeeMe/)。

## Mac 如何 squirrel.custom.yaml 中的 app_options

把 `Raycast.app` 更换为其他你想要获取应用的名称即可

```shell
grep -A 1 "CFBundleIdentifier" /Applications/Raycast.app/Contents/Info.plist
```

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/grep%20%E8%8E%B7%E5%8F%96%20Mac%20%E5%BA%94%E7%94%A8%20app_options.png)

图中框选的 `com.raycast.macos` 就是你想要的值

## 解决 VS Code 快捷键冲突问题

解决 Control + \` 新建终端快捷键冲突，参考文档：[定制呼出方案的快捷键](https://github.com/rime/home/wiki/CustomizationGuide#%E4%B8%80%E4%BE%8B%E5%AE%9A%E8%A3%BD%E5%96%9A%E5%87%BA%E6%96%B9%E6%A1%88%E9%81%B8%E5%96%AE%E7%9A%84%E5%BF%AB%E6%8D%B7%E9%8D%B5)

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Rime-%E5%88%87%E6%8D%A2%E6%96%B9%E6%A1%88%E5%BF%AB%E6%8D%B7%E9%94%AE.png)

## iCloud 同步

2023-12-07 如果你会 Git，那我更推荐推送到 Git 远程仓库方式进行同步，毕竟能清晰的看到每次修改提交记录，当然多一种同步方式也没什么不好的。

参考文档：[同步至 iCloud](https://github.com/ssnhd/rime#%E5%90%8C%E6%AD%A5%E8%87%B3-icloud)

1. 打开 Rime 的配置目录，找到 `installation.yaml` 文件；
2. 添加参数 `sync_dir`，把 `feng` 替换成你自己的管理员名称即可；
3. 更改参数 `installation_id` 这是后续同步的目录名称；
4. 点击菜单栏【ㄓ】-【同步用户数据】；
5. 打开 iCloud 查看是否同步成功。

![](https://cdn.jsdelivr.net/gh/fengstats/blogcdn@main/2023/Rime-%E5%90%8C%E6%AD%A5%20iCloud.png)
