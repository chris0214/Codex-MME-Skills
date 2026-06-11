---
name: mme-reference-lookup
description: Use when Codex needs to look up local MMD/MME documentation, MME syntax, HLSL semantics, annotations, Script commands, STANDARDSGLOBAL, CONTROLOBJECT, DefaultEffect, MMDPass, render target parameters, or framework-specific reference files.
---

# MME Reference Lookup

## Overview

Find and quote or summarize the local source of truth for MME syntax and framework behavior. Do not rely on memory when exact annotations or script semantics matter.

## Search Order

1. Official MME references:
   - `H:\MME编写\Official MME Sample\0.软件包\REFERENCE.txt`
   - `H:\MME编写\Official MME Sample\MME中文参考手册.md`
   - `H:\MME编写\Official MME Sample\MME_HLSL.md`
2. Official sample effects:
   - `Basic\full.fx`
   - `Gaussian\Gaussian.fx`
   - `Mirror\Mirror.fx`
3. Suite shared references:
   - `../mmd-mme-workflow/references/mme-core-reference.md`
   - `../mmd-mme-workflow/references/framework-notes.md`
4. Framework source files:
   - ray-mmd, ExcellentShadow2, sdPBR480 files listed in `example-index.md`.

## Encoding Rules

- Try UTF-8 first for modern Chinese docs and some newer Japanese files.
- Try CP932/Shift-JIS for many Japanese readmes and legacy `.fx` files.
- If text is garbled, do not infer meaning until reread with another encoding.

PowerShell snippets:

```powershell
$t=[Text.Encoding]::UTF8.GetString([IO.File]::ReadAllBytes($p))
$t=[Text.Encoding]::GetEncoding(932).GetString([IO.File]::ReadAllBytes($p))
```

For `MME-Reference翻译版.md`, treat it as a DOCX/ZIP and extract `word/document.xml`.

## Lookup Output

```markdown
Reference lookup:
- Question:
- Source files checked:
- Relevant rule:
- Exact implication for this effect:
- Uncertainty:
```

Keep quotations short. Prefer paraphrase plus file path and line number when available.

## Common Targets

- `STANDARDSGLOBAL`, `ScriptClass`, `ScriptOrder`, `ScriptOutput`
- `RenderColorTarget[n]`, `RenderDepthStencilTarget`, `ClearSetColor`, `ClearSetDepth`, `Clear`, `ScriptExternal`, `Pass`, `LoopByCount`, `LoopEnd`
- pass `Script` with `Draw=Buffer` or `Draw=Geometry`
- `MMDPass`, `UseTexture`, `UseSphereMap`, `UseToon`, `Subset`
- `OFFSCREENRENDERTARGET`, `RENDERCOLORTARGET`, `RENDERDEPTHSTENCILTARGET`
- `CONTROLOBJECT`, `(self)`, `(OffscreenOwner)`
- material texture semantics and MMD sampler preservation
