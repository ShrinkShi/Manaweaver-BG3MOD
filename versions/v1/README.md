# v1 — Eldritch Blast 6 Beams / 六束魔能爆

## 中文
首个实验版本，仅修改魔能爆射线数量的等级成长：1–2级1束、3–4级2束、5–6级3束、7–8级4束、9–10级5束、11–12级6束；13–20级固定6束以兼容等级上限 MOD。

实现方式为静态覆盖 `EldritchBlast` LevelMap（UUID `ecad9e7a-389d-4789-ba69-898cfd34da3c`），不修改 SpellData。后来实机验证发现该静态覆盖在 Patch 8 中未实际生效，因此由 v2 改为 Script Extender 运行时覆盖。

## English
The first experimental build. It only changed Eldritch Blast beam progression: 1 beam at levels 1–2, 2 at 3–4, 3 at 5–6, 4 at 7–8, 5 at 9–10, and 6 at 11–12. Levels 13–20 remained capped at 6 for level-cap mod compatibility.

It used a static override of the `EldritchBlast` LevelMap (UUID `ecad9e7a-389d-4789-ba69-898cfd34da3c`) without replacing SpellData. In Patch 8 testing this static override did not take effect, so v2 moved the implementation to a Script Extender runtime patch.
