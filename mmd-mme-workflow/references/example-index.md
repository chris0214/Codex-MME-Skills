# MME Example Index

Use `rg --files` first, then read only the files relevant to the effect being designed.

## Official Samples

- `H:\MME编写\Official MME Sample\MME_samples_v6\Basic\full.fx`
  - Baseline full model shader with `object`, `object_ss`, `shadow`, `edge`, `zplot` patterns.
- `H:\MME编写\Official MME Sample\MME_samples_v6\Gaussian\Gaussian.fx`
  - Postprocess ping-pong blur and `Draw=Buffer` pass scripts.
- `H:\MME编写\Official MME Sample\MME_samples_v6\Mirror\Mirror.fx`
  - Offscreen mirror target and render-to-texture pattern.
- `H:\MME编写\Official MME Sample\MME_samples_v6\Mirror\MirrorObject.fx`
  - Object-side mirror interaction.

## Modern Effects Sampled

- `H:\MME编写\SOME NEW MME\PowerDOF_v006\PowerDOF.fx`
  - Depth-aware DOF and postprocess chain.
- `H:\MME编写\SOME NEW MME\ikWetFloor\ikWetFloor.fx`
  - Reflective/wet floor accessory pattern.
- `H:\MME编写\SOME NEW MME\ikUnderwater\ikUnderwater.fx`
  - Screen-space water/underwater post effect.
- `H:\MME编写\SOME NEW MME\LightBloom-1.1.1\LightBloom.fx`
  - Bloom extraction and blur.
- `H:\MME编写\SOME NEW MME\PostRimLightToon_v08`
  - Toon rim-light post effect pattern.
- `H:\MME编写\SOME NEW MME\原神面部阴影1.1\GI_FaceShadow.fx`
  - Face-shadow material/control pattern.
- `H:\MME编写\SOME NEW MME\Y_SDF2.0\Y_SDF2.0\ReadmeCN.txt`
  - SDF-based face shadow workflow notes.

## Framework Examples

- ray-mmd 1.5.2:
  - `H:\MME编写\SOME NEW MME\ray-mmd-1.5.2\ray-mmd-1.5.2\ray.fx`
  - `...\ray.conf`
  - `...\ray_advanced.conf`
  - `...\Shader\textures.fxsub`
  - `...\Shader\gbuffer.fxsub`
  - `...\Materials\material_2.0.fx`
  - `...\Materials\material_common_2.0.fxsub`
- ExcellentShadow2:
  - `H:\MME编写\SOME NEW MME\ExcellentShadow2\ExcellentShadow.fx`
  - `...\ExcellentShadowCommonSystem.fx`
  - `...\ExcellentShadowObject.fxsub`
  - `...\ExcellentShadowZBufDraw.fxsub`
  - `...\full_ES.fx`
  - `...\ExShadowSSAO\ExShadowSSAO.fx`
- sdPBR480:
  - `H:\MME编写\SOME NEW MME\sdPBR480\sdPBR.fx`
  - `...\sdPBRGBuffer.fx`
  - `...\shader\sdPBRconfig.fxsub`
  - `...\shader\sdPBRMaterialHead.fxsub`
  - `...\shader\sdPBRMaterialTail.fxsub`
  - `...\material\body\sdPBR_skin.fx`
  - `...\lighting\同じ種類のライトをいくつでも置けるようになりました.txt`

## Mining Heuristics

- Start with official samples for syntax and MME script semantics.
- Use modern examples for practical parameter naming, UI annotations, and compatibility workarounds.
- Use framework examples only after deciding the task belongs inside that framework.
- Compare both the `.fx` and any readme/config/controller assets; many MME effects only make sense as a loaded object plus shader plus tab assignment.
