# mihoyoCodexPets

## 语言与仓库定位

- 默认使用中文回复、中文文档和中文提交信息，除非用户明确要求其他语言。
- 这是一个米哈游相关 Codex pet 资源仓库，不是编程项目；不要添加 `package.json`、包管理器配置、Docker 配置、测试框架、构建脚本或其他应用工程脚手架，除非用户明确要求转型。
- 不需要 Linear/Symphony 工作流、不需要 `docs/README.md` 文档结构、不启用基于 Git hook 的维护性审计提醒。
- 不要创建 `.codex/config.toml`，除非未来出现稳定、可执行的项目级默认配置需求。

## 项目结构

- 最终可用的宠物 spritesheet 放在对应游戏目录下：
  - `GenshinImpact/`
  - `HonkaiStarRail/`
  - `ZenlessZoneZero/`
- 生成过程产物保存在 `.pet-runs/<pet-name>/`。
- 临时或探索性输出保存在 `output/` 或 `temp/`，不要把它们当作最终宠物资源。
- 更新最终宠物资源时，同步维护 `README.md` 的目录索引。

## 宠物生成规则

- 使用已安装的 `hatch-pet` skill 创建、修复、验证、预览和打包 Codex 兼容宠物 spritesheet。
- 新增或修复宠物时，也遵循仓库 skill `.agents/skills/mihoyo-pet-assets/SKILL.md` 中的项目流程。
- 一次宠物生成中必须保持一致的头身比例、轮廓比例、角色身份特征和主配色。
- 背景色应选择目标角色、服装、道具和特效中不存在的颜色；默认优先使用易抠像的绿色，除非该颜色会与目标冲突。
- 不要用本地脚本手绘、拼贴或伪造 pet 视觉内容来替代图像生成；本地脚本只用于 hatch-pet 流程中的确定性处理、校验、预览和打包。

## 资源质量

- 最终 spritesheet 应是 Codex pet 可用的 8x9 动画图集，透明背景，未使用格保持透明。
- 接受最终资源前，检查 contact sheet、预览视频、`validation.json` 和 `review.json`。
- 重点检查角色身份一致性、头身比例一致性、帧间间距、透明背景清理、是否有断肢/裁切/串格/漂浮伪影。
- 若新增或替换最终 `.webp`，保留对应 `.pet-runs/<pet-name>/` 记录，方便之后追踪 prompt、参考图和 QA 结果。

## 安全与变更边界

- 保留用户已有改动；不要删除、重置或覆盖未明确要求移除的资源、生成记录或临时文件。
- 不要提交、推送或创建 PR，除非用户明确要求。
- 对 `.pet-runs/`、`output/`、`temp/` 这类生成产物做清理前，先说明目标并确认不会删除仍需追踪的源素材或 QA 记录。
