# 上传车次资料包

[打开本目录的 GitHub 上传页](https://github.com/zqshi0911/northbound-rail-race/upload/main/docs/content/services)

每个文件为 UTF-8 `.json`，最外层须含 `schemaVersion: 1`、`id`、`version`、`title` 和非空 `services`。车次引用已存在的线路 `routeId`，无需复制原线路。新线路包应先上传；同一个线路包也可以同时提供车次，避免依赖顺序问题。

每个车次填写真实车次号、方向、首末站、版本说明、核验日期、公开来源网址及按实际方向排列的到发时刻。反向必须另填独立表，不能把去程时刻倒过来。通过时刻放入 `passTimes`，并随本包新车次一起提供；只有有真实来源的 `published` 通过时刻参与正点计分。

参考模板：`../examples/service-template.json.example`。模板中的钟点是虚构练习内容，来源字段含明确待替换占位符，因此不能直接装入游戏；请换成核验过的真实资料后再另存为 `.json` 上传。未公开的钟点不要插值编造。

提交后点游戏选择页“检查更新”。每次修订使用新车次 ID，保留旧 ID 和旧数据；只提高版本号不能覆盖旧对象。详细字段见 `../schemas/rail-content-pack.schema.json` 和源码包“资料说明/rail-content-library.md”。
