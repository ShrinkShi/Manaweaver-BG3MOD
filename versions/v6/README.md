# v6 — Independent Manaweaver Progression / 独立魔能术士成长线

## 中文
v6 进一步把魔能术士与原版邪术师成长分离：选择魔能术士后不再出现魔契三选一，也不再进入原版魔能祈唤选择；其他邪术师子职业保持原版成长。

魔能术士拥有独立9项被动池：苦痛魔爆、斥力魔爆、魔能长枪、术法魔爆、噬法魔爆、汲魂魔爆、追袭魔爆、虚弱魔爆、终极魔爆。

同时彻底移除术法点体系：术法魔爆改为三个开关，每一层、每一束直接消耗一个 Warlock Pact Slot，并按法术位等级增伤：1环+1、2环+1d6、3环+1d6+1、4环+1d12+1、5环+2d12、6环及以上+2d12+1。噬法魔爆改为击杀恢复1个契约法术位。

## English
v6 further separates Manaweaver progression from the vanilla Warlock. Manaweaver no longer receives the Pact Boon three-way choice or the vanilla Eldritch Invocation selector, while other Warlock subclasses retain their normal progression.

Manaweaver receives its own nine-passive pool: Agonizing Blast, Repelling Blast, Eldritch Spear, Metamagic Blast, Spell-Eating Blast, Soul-Draining Blast, Pursuit Blast, Weakening Blast and Ultimate Blast.

The Sorcery Point system is removed completely. Metamagic Blast becomes three toggles that consume one Warlock Pact Slot per beam per active tier, with bonus damage based on slot level: 1st +1, 2nd +1d6, 3rd +1d6+1, 4th +1d12+1, 5th +2d12, 6th+ +2d12+1. Spell-Eating Blast now restores one pact slot on a kill.

## Source archive / 源码归档
This historical source snapshot is split into three `.tar.xz` parts. Generated binary `.loca` files are omitted; the editable `.loca.xml` localization source is retained.

本历史源码快照拆分为三个 `.tar.xz` 分片。生成的二进制 `.loca` 未包含，但保留了可编辑的 `.loca.xml` 本地化源码。

```bash
cat Manaweaver_v6_source.tar.xz.part-* > Manaweaver_v6_source.tar.xz
tar -xJf Manaweaver_v6_source.tar.xz
```
