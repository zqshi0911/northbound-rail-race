# 资料包格式

`rail-content-pack.schema.json` 使用 JSON Schema Draft 2020-12，供支持 JSON Schema 的编辑器检查资料包字段。

本目录不被资料扫描器当作线路或车次目录读取。模板可以在最外层加 `"$schema": "../schemas/rail-content-pack.schema.json"` 供编辑器定位；程序实际加载时仍按内置校验及注册事务判定。

跨字段关系（例如 `toKm > fromKm`、站点属于所引用的线路、反向有独立时刻、限速随本包新线路提供）和跨文件累计上限，需要程序进一步检查，无法只靠这个静态 Schema 完整判定。
