# 格式模板，不自动加载

- `synthetic-route.json.example`：可通过结构校验的虚构练习轨道示例，无真实车次、无伪造来源。它不会被自动扫描。
- `service-template.json.example`：车次字段模板，时刻为虚构练习钟点；`REPLACE_WITH_VERIFIABLE_PUBLIC_SOURCE_URL` 必须改成核验过的真实来源，才能通过来源校验。
- `speed-and-pass-template.json.example`：随新线路与新车次提供限速／通过时刻的字段模板；来源占位符同样必须替换。不能把模板中的演示速度或钟点当作已核验资料。

这些文件特意使用 `.json.example`，不是 `.json`。不要把整个 `examples` 目录移入 `routes` 或 `services`。使用模板时，先复制到工作目录，核验真实轨迹、车次及来源，检查所有关联 ID，然后另存为新 `.json` 文件上传。

`schemas/rail-content-pack.schema.json` 校验字段形状；运行程序还会检查真实轨道公里、首末站、停站次序、引用关系、重复 ID 和累计资源上限。结构合格不等于内容真实。
