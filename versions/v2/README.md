# v2 — Runtime 6-Beam Eldritch Blast / 运行时六束魔能爆

## 中文
保留 v1 的六束成长表，但放弃未生效的静态 LevelMap 覆盖，改用 Norbyte BG3 Script Extender 在 `StatsLoaded` / `SessionLoaded` 阶段运行时修改 `EldritchBlast` LevelMap。

这是第一版经实机验证成功的实现，确立了后续版本的 Script Extender 运行时架构。需要 BG3 Script Extender。

## English
Keeps the v1 six-beam progression but replaces the ineffective static LevelMap override with a Norbyte BG3 Script Extender runtime patch applied during `StatsLoaded` / `SessionLoaded`.

This was the first implementation verified successfully in-game and became the runtime architecture used by later versions. BG3 Script Extender is required.
