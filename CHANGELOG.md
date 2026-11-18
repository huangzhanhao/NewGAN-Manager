# 更新日志

本项目的显著变更记录在此文件中。版本号与仓库根目录的 `version` 文件一致；
Linux `.deb` 打包时该文件会作为软件包 changelog 随包分发，因此不要删除或改名。

## 1.5

- **多 Profile 管理**：一个存档一套配置，切换 Profile 时自动交换 `config.xml` 快照
- **服务层拆分**：`services/` 下拆出 player / profile / replace 三个服务，GUI 只做输入输出与线程调度
- **中文数据库支持**：识别中文表头与中文国籍，经 `.config/nat_translation.json` 翻译回三字码
- **只处理随机人**：按 RTF 最后一列（`是/否`、`Yes/No`）过滤
- **三种替换模式**：`Preserve` / `Overwrite` / `Generate`
- **应用内日志面板**：按级别筛选、一键打开日志文件，日志 10 MB × 3 份滚动
- **用户数据便携化**：运行时数据写入应用目录 `data/`，不可写时回退平台标准数据目录，旧版数据自动迁移
- **首次启动容错**：`cfg.json` 缺失或损坏时回退默认配置，损坏文件备份为 `.corrupt` 保留证据
- **CI 重建**：`ci.yml` 单测门禁 + `windows.yml` / `linux.yml` / `macos.yml` 三端构建 + `release.yml` 汇总出 Release
- **依赖口径统一**：toga 0.5.7 线，`requires-python` 收敛为 3.12+

## 1.4 及更早

上游 [Maradonna90/NewGAN-Manager](https://github.com/Maradonna90/NewGAN-Manager) 的历史版本，见该仓库的提交记录。
本 fork 自此版本起独立演进，变化集中在多 Profile、中文 RTF、便携化数据目录与 CI。
