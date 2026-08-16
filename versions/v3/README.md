# v3 — Progressive Eldritch Blast / 渐进魔能爆

## 中文
将魔能爆从单纯“增加束数”改为逐束渐进伤害。1级1d10；2级两束1d10；3级1d12+1d10；4级两束1d12；5级三束（1d12/1d12/1d10）；6–8级逐步把三束升级为 d14；9–12级逐步升级为 d16，11级保持10级配置。

BG3 原生不存在 d14/d16，因此采用等平均值近似：d14→1d12+1，d16→1d12+2。Script Extender 在 DealDamage 阶段只替换魔能爆本体的基础 1d10，以尽量保留苦痛魔爆、Hex、强能法袍等附加机制。

## English
Changes Eldritch Blast from pure beam-count scaling into per-beam progressive damage. Level 1 starts at 1d10; level 2 has two 1d10 beams; level 3 uses 1d12/1d10; level 4 uses two 1d12 beams; level 5 adds a third beam, and levels 6–12 progressively raise beam dice toward d14 and d16.

BG3 has no native d14/d16 dice, so equal-average approximations are used: d14 → 1d12+1 and d16 → 1d12+2. Script Extender intercepts the base Eldritch Blast `1d10` DealDamage functor to preserve riders such as Agonizing Blast, Hex and Potent Robe as much as possible.
