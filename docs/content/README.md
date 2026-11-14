# 独立资料目录

新版程序安装一次后，以后可以只上传新文件。提交后，在游戏的线路选择页点击“检查更新”。无需重新生成 `game.js`，也无需修改清单或安装 GitHub Actions。

| 内容 | 仓库目录 | 可直接上传的文件 |
| --- | --- | --- |
| 音乐 | `docs/content/music/` | `.mp3`、`.ogg`、`.wav`、`.m4a`、`.flac` |
| 线路与随线限速 | `docs/content/routes/` | 符合资料包规范的 `.json`，须含非空 `routes` |
| 车次与随车通过时刻 | `docs/content/services/` | 符合资料包规范的 `.json`，须含非空 `services` |

- [上传一首音乐](https://github.com/zqshi0911/northbound-rail-race/upload/main/docs/content/music)
- [上传线路资料包](https://github.com/zqshi0911/northbound-rail-race/upload/main/docs/content/routes)
- [上传车次资料包](https://github.com/zqshi0911/northbound-rail-race/upload/main/docs/content/services)

新线路和车次使用新 ID。修订旧资料时，新版本保留旧对象原文，再追加新 ID；单纯修改 `version` 不能覆盖旧 ID。保留旧文件和旧对象，才能继续识别旧交路及其成绩分组。

示例放在 `examples/*.json.example`，不会自动进入游戏。正式格式见 `schemas/rail-content-pack.schema.json`；完整说明见源码包“资料说明/rail-content-library.md”。主项目在 `public/content/` 维护这些文件，网页上传版中对应 `docs/content/`。

音乐直接上传音频文件即可，无需同时上传描述 JSON。文件名会显示为曲名。线路和车次的 JSON 必须使用 UTF-8、`schemaVersion: 1`，单文件不超过 8 MiB。
