# v7 — Fear Blast & Exclusive Spellbook / 恐惧魔爆与专属法表

## 中文
v7 将“术法魔爆”替换为**恐惧魔爆**：每束魔能爆命中时，目标进行固定 DC10 魅力豁免，失败则恐惧1回合。

新增魔能术士专属法表，并加入三个原创法术：
- **魔能爆裂（2环）**：2d12力场伤害、2米爆炸范围；智力与魅力双豁免，任一成功则半伤；每升一环+1d12；射程随魔能长枪一起增强。
- **魔爆倾泻（3环）**：3环8束、4环10束、5环12束；追袭魔爆额外+1束。所有射线锁定同一目标，基础伤害仅1点，但逐束进入所有魔爆被动管线。
- **魔能湮灭（6环）**：以秘奥法术形式每长休一次。将自身HP降至1，按损失生命/2生成射线，基础最多12束，随机攻击12米内所有生物、不分敌我；斥力将目标推出12米时追加追射，每束命中额外获得1点临时生命。

v7 引入的二进制 `.loca` 文本区偏移存在错误，导致游戏UI出现本地化串位/乱码；该问题在 v8 修复。

## English
v7 replaces Metamagic Blast with **Fear Blast**: every Eldritch Blast beam that hits forces a fixed DC 10 Charisma save; failure applies Frightened for one round.

Manaweaver receives an exclusive spell list and three custom spells:
- **Eldritch Detonation (2nd level):** 2d12 Force in a 2m explosion; both Intelligence and Charisma saves are rolled and either success halves damage; +1d12 per upcast level; range scales with Eldritch Spear.
- **Eldritch Barrage (3rd level):** 8 beams at 3rd, 10 at 4th, 12 at 5th; Pursuit Blast adds one more. All beams are locked to the same target, deal only 1 base Force damage, but each beam enters the full Eldritch Blast passive pipeline.
- **Eldritch Annihilation (6th-level Mystic Arcanum):** once per long rest. Set the caster to 1 HP and fire `floor(HP lost / 2)` rays, capped at 12 base rays, at creatures within 12m regardless of allegiance. Repelling Blast pushing a target outside 12m grants a follow-up ray; each hit grants 1 extra temporary HP.

v7 shipped with an incorrect binary `.loca` text offset that caused localization corruption in the UI. v8 fixes this.

## Source archive / 源码归档
This source snapshot is split into three `.tar.xz` parts. Generated binary `.loca` files are omitted; editable `.loca.xml` files are retained.

```bash
cat Manaweaver_v7_source.tar.xz.part-* > Manaweaver_v7_source.tar.xz
tar -xJf Manaweaver_v7_source.tar.xz
```
