# MME-SKILLS

这是一个面向 MMD/MME 效果编写的 Codex Skills 套件。

它把 MikuMikuEffect 的 `.fx` / `.fxsub` 编写流程拆成多个阶段：理解用户想要的画面效果、判断实现路线、查找本地参考、挖掘现有效果示例、编写 shader、静态审查，以及根据 MMD/MME 的实际表现进行调试。

套件里也整理了 ray-mmd、ExcellentShadow2、sdPBR 这类复杂 MME 框架的使用和排错要点。它的目标不是替代这些框架，而是让 Codex 在协助编写 MME 时更懂它们的结构、加载方式和常见坑。

## 技能列表

- `mmd-mme-workflow`：总控技能，负责组织完整的 MME 编写工作流。
- `mme-effect-assessment`：把用户描述的视觉效果整理成明确的效果需求。
- `mme-effect-feasibility`：判断效果适合独立实现，还是应该基于 ray-mmd、sdPBR、ExcellentShadow 等框架扩展。
- `mme-implementation-planning`：规划文件结构、渲染目标、Pass、控制器参数和调试点。
- `mme-reference-lookup`：查找 MME 语法、参数、注解和框架规范。
- `mme-example-mining`：从本地已有 MME 示例中寻找可复用的实现模式。
- `mme-authoring`：根据计划编写或修改 `.fx` / `.fxsub` 文件。
- `mme-static-review`：在运行测试前检查 shader、MME Script、RenderTarget、include、编码和框架集成问题。
- `mme-runtime-debugging`：诊断黑屏、空输出、编译报错、绘制顺序错误、控制器失效、框架加载错误等运行时问题。

## 安装方式

把这些技能目录复制到 Codex 的 skills 目录即可。Windows 下通常是：

```powershell
$skills = @(
  "mmd-mme-workflow",
  "mme-effect-assessment",
  "mme-effect-feasibility",
  "mme-implementation-planning",
  "mme-reference-lookup",
  "mme-example-mining",
  "mme-authoring",
  "mme-static-review",
  "mme-runtime-debugging"
)

foreach ($skill in $skills) {
  Copy-Item -LiteralPath ".\$skill" -Destination "$env:USERPROFILE\.codex\skills\$skill" -Recurse -Force
}
```

复制完成后，重启 Codex 或刷新技能列表。

## 使用建议

如果你只是想让 Codex 协助完成一个 MME 效果，通常从总控技能开始：

```text
使用 $mmd-mme-workflow，帮我设计并编写一个 MME 效果。
```

如果你已经知道自己要做哪一步，也可以直接调用某个阶段技能。例如：

```text
使用 $mme-reference-lookup，帮我查一下 MME 的 RenderColorTarget 和 Draw=Buffer 写法。
```

```text
使用 $mme-runtime-debugging，帮我排查这个 MME 黑屏问题。
```

## 参考资料说明

本仓库只包含为 Codex 编写的 Skill 文档和简明参考笔记，不包含其他第三方资源。

这些 Skill 的参考笔记来自本地 MME 文档和本地效果示例的阅读整理，目的是帮助 Codex 更准确地查找和使用你自己电脑上的资料。

如果你准备把这个仓库公开发布，建议不要把第三方 MME 效果包直接放进仓库，除非它们的许可证明确允许再分发。

## 开源协议

本项目使用 MIT License。详见 [LICENSE](LICENSE)。
