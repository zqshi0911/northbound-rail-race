# 上传线路资料包

[打开本目录的 GitHub 上传页](https://github.com/zqshi0911/northbound-rail-race/upload/main/docs/content/routes)

每个文件为 UTF-8 `.json`，最外层须含 `schemaVersion: 1`、`id`、`version`、`title` 和非空 `routes`。线路包可以同时带 `services`、`speedSegments`、`passTimes`，以便一次提交整条线路及车次。

程序自动生成线路反向；线路基础 ID 不能以 `-reverse` 结尾。反向车次必须提供独立真实时刻表。正反向限速需要分别写明 `routeId` 和从该方向起点计算的公里，不能只写一份后假定自动反转。

`speedSegments` 必须随本包的新线路一起提供；修订已有线路限速时，用新的线路 ID 和对应限速数据保留版本差异。线路必须使用有序真实轨道坐标，保留来源与许可；JSON 格式通过不代表轨迹或来源已经核实。

参考模板：`../examples/synthetic-route.json.example`。这是明确标注的虚构练习轨道，不是现实线路或图定资料；模板扩展名不会被自动扫描。

提交后点游戏选择页“检查更新”。旧 ID 不会被覆盖；新增或修订使用新 ID。详细字段见 `../schemas/rail-content-pack.schema.json` 和源码包“资料说明/rail-content-library.md”。
