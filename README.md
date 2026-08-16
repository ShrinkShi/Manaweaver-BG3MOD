# Manaweaver / 魔能术士 — Baldur's Gate 3 Patch 8

[中文](#中文) | [English](#english)

> A Patch 8 Warlock overhaul mod that grew from an Eldritch Blast experiment into a complete custom subclass.
>
> 一个面向《博德之门3》Patch 8 的邪术师重制 MOD：项目最初只是魔能爆强化实验，现已发展为完整的自定义子职业——**魔能术士（Manaweaver）**。

**Current version / 当前版本：v8**  
**Target / 目标版本：Baldur's Gate 3 Patch 8**  
**Requires / 需要：Norbyte BG3 Script Extender**  
**Module UUID：`8255350e-db90-430a-826b-98fb79372b69`**

---

# 中文

## 1. 项目简介

Manaweaver-BG3MOD 是一个围绕 **魔能爆（Eldritch Blast）** 重构邪术师玩法的 Patch 8 MOD。

项目 v1–v4 主要研究如何突破原版魔能爆的成长方式；从 v5 开始，MOD 被重构为真正的邪术师子职业——**魔能术士**。它放弃原版邪术师的魔契与普通魔能祈唤成长路线，改为一套围绕魔能爆、生命代价、死亡爆发和专属法术构成的独立成长体系。

当前 v8 的设计目标不是严格复刻 D&D 5e 桌游强度，而是提供一个具有鲜明职业特色、明显高于普通单职业强度、但通过资源和复活限制避免无限循环的单机 Power Fantasy 子职业。

---

## 2. 安装要求

- Baldur's Gate 3，目标版本为 **Patch 8**。
- **Norbyte BG3 Script Extender**。
- 推荐使用 **BG3 Mod Manager** 导入并启用 `.pak`。
- 导入 MOD 后，请确认其位于 Active Mods，并保存加载顺序。
- 涉及子职业 Progression 的版本更新后，推荐找威瑟斯完整洗点，再从邪术师1级重新升级测试。

本仓库当前主要用于保存 **源码与版本历史**。历史源码位于 [`versions/`](versions/) 目录。

---

## 3. 当前 v8：魔能术士核心规则

### 魔能爆基础束数

| 总角色等级 | 基础束数 | 点出追袭魔爆后 |
|---|---:|---:|
| 1–4 | 1 | 2 |
| 5–8 | 2 | 3 |
| 9–12 | 3 | 4 |

**追袭魔爆**增加的射线可以与原本的射线攻击同一个目标。

### 独立成长路线

魔能术士不会获得原版邪术师的：

- 魔契三选一；
- 原版魔能祈唤选择。

其他邪术师子职业不受影响，仍然保留原版成长。

魔能术士在以下等级获得一次专属“魔能被动”选择：

**1、3、5、6、8、9、10、11、12级，共9次。**

---

## 4. 九项魔能被动

### 苦痛魔爆 / Agonizing Blast

将魅力调整值加入魔能爆伤害，并兼容魔能术士的派生魔爆射线。

### 斥力魔爆 / Repelling Blast

魔能爆命中后击退目标。魔能爆倾泻、魔能湮灭和魔能之心等派生射线也进入同一魔爆机制。

### 魔能长枪 / Eldritch Spear

提高魔能爆射程，并同步强化需要继承魔能爆射程的专属法术，例如魔能爆裂与魔爆倾泻。

### 恐惧魔爆 / Fear Blast

每一束实际命中的魔能爆都会使目标进行一次 **DC 10 魅力豁免**；失败则恐惧1回合。

### 噬法魔爆 / Spell-Eating Blast

点出后默认开启。魔能爆直接击杀单位时恢复 **1个邪术师契约法术位**。

v8 平衡限制：**每个战斗轮最多成功恢复1个契约法术位**。如果触发击杀时契约法术位已经满额，则不会浪费本轮的返还额度。

### 汲魂魔爆 / Soul-Draining Blast

每一束实际命中的魔能爆恢复 **1点生命值**。

### 追袭魔爆 / Pursuit Blast

普通魔能爆永久额外增加 **1束射线**，并允许额外射线与其他射线攻击同一目标。

### 虚弱魔爆 / Weakening Blast

每束命中随机选择目标的力量、敏捷、体质、智力、感知或魅力之一，使其 **-1，持续1回合，并可叠加**。

### 终极魔爆 / Ultimate Blast

同一个目标在同一战斗轮内受到第4束魔能爆命中时，以该目标为中心触发一次约4米范围的力场爆炸。

| 角色等级 | 爆炸伤害 |
|---|---:|
| 1–5 | 1d12 Force |
| 6–9 | 2d12 Force |
| 10–12 | 3d12 Force |

每个目标每回合最多触发一次。

---

## 5. 子职业固有能力

### 1级：魔能诅咒 / Mana Curse

魔能赋予邪术师异常强大的力量，同时也反噬其肉体：

- 最大生命值降低50%；
- 获得 +1 AC。

### 1级：魔能之心 / Mana Heart

魔能聚集在角色心脏中。死亡时，以自身为中心对5米内生物释放魔能爆，**不分敌我**。

初始射线总数等于当前一次普通魔能爆能够发射的束数，因此会受到等级和追袭魔爆影响。

### 5级：魔能诅咒 II / Mana Curse II

- 最大生命值仍降低50%；
- 失去1级时的额外 +1 AC。

### 5级：魔能之心 II / Mana Heart II

保留魔能之心的死亡爆发，并增加连锁机制：

- 心脏魔爆直接击杀一个目标后，额外追加1束；
- 若拥有追袭魔爆，则每次击杀追加2束；
- 新增射线继续击杀目标时会继续生成射线。

实现中保留技术安全上限，避免异常 MOD 联动造成无限递归。

### 11级：魔能精通 / Mana Mastery

魔能术士已经完全掌控体内的魔能：

- 移除之前的魔能诅咒，生命上限恢复正常；
- 魅力调整值加入 AC；
- 每束魔能爆命中获得1点临时生命；
- 魔能爆被目标闪避 / Miss 后获得1个附赠动作；
- 借机攻击改为释放一次完整魔能爆，而非普通武器攻击。

v8 平衡限制：**Miss 获得附赠动作每个战斗轮最多触发1次。**

### 11级：魔能之心 III / Mana Heart III

继承魔能之心 II 的全部死亡连锁能力，并新增：

- 如果死亡魔爆至少直接击杀1个目标，则角色以 **1 HP** 复活；
- 每额外击杀1个目标，额外获得 **24点临时生命值**；
- 被魔能之心 III 复活后，下一次戏法的重击判定所需点数 -1。

v8 平衡限制：

- 每场战斗最多复活1次；
- 每次长休之间最多复活3次；
- 即使复活次数耗尽，死亡时的魔能之心爆发仍会执行，只是不再复活角色。

---

## 6. 魔能术士专属法表

### 戏法

- 魔能爆

### 1环

- 灾祸术
- 哈达之臂
- 脆弱诅咒
- 大步奔行
- 羽落术
- 强化跳跃
- 脚底抹油
- 云雾术
- 防护善恶

### 2环

- 失明术
- 朦胧术
- 秘法锁
- 强化属性
- 侦测思想
- 人类定身术
- 沉默术
- 迷踪步
- 暗黑术
- 黑暗视觉
- 迷魂术
- 疯狂冠冕
- **魔能爆裂（新增）**

### 3环

- 法术反制
- 恐惧术
- 催眠图纹
- 死者交谈
- 臭云术
- 吸血鬼之触
- **魔爆倾泻（新增）**

### 4环

- 任意门
- 困惑术
- 死亡防护
- 高等隐身术
- 行动自如

### 5环

- 怪物定身术
- 疫病术
- 死云术
- 支配人类

### 6环

- **魔能湮灭（新增）**

---

## 7. 三个原创法术

### 魔能爆裂 / Eldritch Detonation — 2环

- 基础伤害：2d12 Force；
- 爆炸半径约2米；
- 基础施法距离与魔能爆一致，并受到魔能长枪强化；
- 目标依次进行智力与魅力豁免；
- 两次都失败：全额伤害；
- 任意一次成功：半伤；
- 每提高1个法术环位，伤害增加1d12。

### 魔爆倾泻 / Eldritch Barrage — 3环

选择一个目标后，对该目标自动连续发射多束“基础伤害为1点 Force”的魔爆派生射线：

| 法术环位 | 基础束数 | 追袭魔爆后 |
|---|---:|---:|
| 3环 | 8 | 9 |
| 4环 | 10 | 11 |
| 5环 | 12 | 13 |

每一束独立进行攻击判定，并进入苦痛、斥力、恐惧、噬法、汲魂、虚弱、终极魔爆及魔能精通等相关事件链。

### 魔能湮灭 / Eldritch Annihilation — 6环秘奥法术

- 每次长休可施放1次；
- 不消耗普通契约法术位；
- 将自身当前生命值降低至1；
- 射线数量 = `floor(损失生命值 / 2)`；
- 基础射线最多12束；
- 在自身12米范围内随机选择生物作为目标，**不分敌我**；
- 如果斥力魔爆将目标推出12米范围，对该目标额外追加1束追射；
- 每一束湮灭射线命中，额外获得1点临时生命。

为了避免异常递归，技术射线总数设置了安全上限。

---

## 8. 当前强度定位

Manaweaver 是一个明显高于普通原版单职业强度的 Power Fantasy 子职业。

它的强度并不只来自魔能爆本体伤害，而来自：

**高攻击次数 + 逐束控制 + 属性削弱 + 击退 + 回复 + 临时生命 + 资源返还 + 死亡反击 + 复活 + 行动经济。**

v8 对三个最容易形成无限循环的节点加入了限制：

1. 魔能精通的 Miss 附赠动作每轮最多1次；
2. 噬法魔爆的契约位返还每轮最多1次；
3. 魔能之心 III 每战最多复活1次、每长休最多3次。

这并不会把职业压回“原版平均强度”，但显著降低无限行动、无限资源和无限复活闭环的风险。

---

## 9. 版本历史 / Source History

每个版本都有独立目录和说明：

| 版本 | 主要变化 | 源码 |
|---|---|---|
| v1 | 静态 LevelMap 六束魔能爆实验；实机未生效 | [`versions/v1`](versions/v1/) |
| v2 | 改用 Script Extender 运行时 LevelMap，六束版本实机成功 | [`versions/v2`](versions/v2/) |
| v3 | 渐进魔能爆；逐束不同伤害骰；d14/d16 等平均值近似 | [`versions/v3`](versions/v3/) |
| v4 | 魔爆专精体系；首次加入6个原创魔爆被动和术法点实验 | [`versions/v4`](versions/v4/) |
| v5 | 重构为真正的魔能术士子职业；加入魔能诅咒/魔能之心/魔能精通 | [`versions/v5`](versions/v5/) |
| v6 | 独立成长线；移除魔契和原版祈唤；术法点改为契约法术位体系 | [`versions/v6`](versions/v6/) |
| v7 | 术法魔爆→恐惧魔爆；加入专属法表及3个原创法术；存在 LOCA 偏移缺陷 | [`versions/v7`](versions/v7/) |
| **v8** | **修复本地化二进制偏移；加入行动/资源/复活三项平衡限制；当前最新版** | [`versions/v8`](versions/v8/) |

### v1

最初只尝试把原版魔能爆改成“每2级增加一束，12级6束”。静态 LevelMap 覆盖在 Patch 8 实机中未生效。

### v2

转向 Script Extender，在运行时覆写 `EldritchBlast` LevelMap。该方案通过实机验证，确立后续版本的技术路线。

### v3

探索“不同射线拥有不同伤害骰”。由于 BG3 原生没有 d14/d16，使用 `1d12+1` 与 `1d12+2` 作为等平均值近似。

### v4

从单个法术强化发展为“魔爆专精系统”。首次加入术法魔爆、噬法魔爆、汲魂魔爆、追袭魔爆、虚弱魔爆、终极魔爆。

### v5

将整个系统收束为真正的邪术师子职业“魔能术士”。建立1/5/11级的魔能诅咒、魔能之心和魔能精通成长链。

### v6

魔能术士开始拥有真正独立的职业成长：不再获得魔契，也不能选择普通魔能祈唤，只能从自己的九项魔能被动中成长。同时推翻术法点设计，改为直接使用契约法术位。

### v7

将术法魔爆替换为恐惧魔爆，并加入完整专属法表、魔能爆裂、魔爆倾泻、魔能湮灭。该版本的 `.loca` 生成器误将条目步长按74字节计算，造成中文UI名称与描述错位。

### v8

修复 LOCA 条目大小为正确的70字节，并增加二进制反向读取校验。同时加入三项平衡限制，是当前源码基线。

---

## 10. 调试

v8 Script Extender 调试命令：

```text
!sr_eb_v8_dump
```

运行时日志目录通常位于：

```text
%LOCALAPPDATA%\Larian Studios\Baldur's Gate 3\Script Extender\Shrink_EldritchSorcerer_Patch8_v8\
```

---

## 11. 已知边界

- 本项目持续以 Patch 8 实机测试结果修正实现，不保证与所有职业重制、等级上限、法术重制或 Script Extender MOD 完全兼容。
- 自定义2/3环法术在复杂多职业情况下的升环位识别仍建议继续进行实机校准。
- v7 是明确存在本地化损坏的历史版本，仅用于保存开发历史；实际游玩应使用 v8 或后续版本。

---

## 12. License

本项目使用仓库中的 **GNU General Public License v3.0 (GPL-3.0)**。

---

# English

## 1. Overview

Manaweaver-BG3MOD is a Patch 8 Warlock overhaul centered on **Eldritch Blast**.

Versions v1–v4 were experiments in changing Eldritch Blast scaling and per-beam behavior. Starting with v5, the project became a true Warlock subclass: **Manaweaver**. Instead of following the vanilla Pact Boon and Eldritch Invocation progression, Manaweaver uses a dedicated system built around Eldritch Blast passives, life sacrifice, death-triggered barrages, recovery loops and an exclusive spell list.

The current v8 is intentionally a Power Fantasy subclass rather than a strict tabletop-balance conversion. It is designed to feel substantially stronger than a normal single-class character while using explicit limits to prevent infinite action, resource and revival loops.

---

## 2. Requirements & Installation

- Baldur's Gate 3, targeting **Patch 8**.
- **Norbyte BG3 Script Extender**.
- **BG3 Mod Manager** is recommended for importing and enabling the `.pak`.
- Make sure the mod is in Active Mods and save the load order.
- After updates that alter subclass progression, a full Withers respec from Warlock level 1 is recommended for testing.

This repository primarily stores **source code and version history**. Historical source snapshots are available under [`versions/`](versions/).

---

## 3. Current v8: Core Manaweaver Rules

### Eldritch Blast beam progression

| Total character level | Base beams | With Pursuit Blast |
|---|---:|---:|
| 1–4 | 1 | 2 |
| 5–8 | 2 | 3 |
| 9–12 | 3 | 4 |

The beam added by **Pursuit Blast** may target the same creature as the other beams.

### Independent subclass progression

Manaweaver does **not** receive the vanilla Warlock:

- Pact Boon three-way choice;
- vanilla Eldritch Invocation selector.

Other Warlock subclasses keep their normal progression.

Manaweaver gains one dedicated Mana/Eldritch passive choice at levels:

**1, 3, 5, 6, 8, 9, 10, 11 and 12 — nine choices total.**

---

## 4. The Nine Eldritch Passives

### Agonizing Blast
Adds the Charisma modifier to Eldritch Blast damage and is extended to Manaweaver's derived Eldritch rays.

### Repelling Blast
Pushes targets hit by Eldritch Blast. Derived rays from Mana Heart, Eldritch Barrage and Eldritch Annihilation enter the same blast pipeline.

### Eldritch Spear
Extends Eldritch Blast range and also affects custom spells designed to inherit Eldritch Blast range, such as Eldritch Detonation and Eldritch Barrage.

### Fear Blast
Every Eldritch Blast beam that actually hits forces a **DC 10 Charisma saving throw**. On failure, the target is Frightened for one round.

### Spell-Eating Blast
Enabled by default when learned. A direct Eldritch Blast kill restores **one Warlock Pact Slot**.

v8 balance limit: **at most one successful pact-slot refund per combat round**. If pact slots are already full, the kill does not consume that round's refund allowance.

### Soul-Draining Blast
Each Eldritch Blast beam that hits restores **1 HP**.

### Pursuit Blast
Permanently adds **one beam** to normal Eldritch Blast and allows that beam to target the same creature as the other rays.

### Weakening Blast
Each hit randomly reduces Strength, Dexterity, Constitution, Intelligence, Wisdom or Charisma by **1 for one round**, stacking with additional hits.

### Ultimate Blast
When the same target is hit by the fourth Eldritch Blast beam in the same combat round, a roughly 4m Force explosion is triggered around that target.

| Character level | Explosion damage |
|---|---:|
| 1–5 | 1d12 Force |
| 6–9 | 2d12 Force |
| 10–12 | 3d12 Force |

Each target can trigger the explosion at most once per round.

---

## 5. Subclass Features

### Level 1 — Mana Curse
Power comes at a physical cost:

- Maximum HP reduced by 50%;
- +1 AC.

### Level 1 — Mana Heart
When the Manaweaver dies, the mana concentrated in the character's heart erupts and fires Eldritch Blast-derived rays at creatures within 5m, **regardless of allegiance**.

The initial ray count equals the number of beams the character's normal Eldritch Blast would currently fire, including Pursuit Blast.

### Level 5 — Mana Curse II
- Maximum HP remains reduced by 50%;
- the level-1 +1 AC bonus is removed.

### Level 5 — Mana Heart II
Keeps the death barrage and adds recursive chaining:

- a direct Mana Heart ray kill adds one extra ray;
- with Pursuit Blast, each kill adds two rays;
- kills caused by added rays may continue the chain.

A technical safety cap prevents abnormal mod interactions from causing infinite recursion.

### Level 11 — Mana Mastery
The Manaweaver finally controls the power completely:

- removes the Mana Curse and restores normal maximum HP;
- adds Charisma modifier to AC;
- every Eldritch Blast hit grants 1 temporary HP;
- an Eldritch Blast miss grants a bonus action;
- opportunity attacks cast a full Eldritch Blast instead of performing a normal weapon attack.

v8 balance limit: **the bonus action from misses can trigger at most once per combat round.**

### Level 11 — Mana Heart III
Keeps all Mana Heart II behavior and adds:

- if the death barrage directly kills at least one target, revive at **1 HP**;
- gain **24 temporary HP** for every additional kill;
- after revival, the next cantrip has its critical-hit threshold reduced by 1.

v8 balance limits:

- at most one Mana Heart III revival per combat;
- at most three revivals between long rests;
- the death barrage still fires after the revival quota is exhausted — only the revival is disabled.

---

## 6. Exclusive Manaweaver Spell List

### Cantrip
- Eldritch Blast

### 1st Level
Bane, Arms of Hadar, Hex / curse-themed utility, Longstrider, Feather Fall, Enhance Leap, Grease, Fog Cloud, Protection from Evil and Good.

### 2nd Level
Blindness, Blur, Arcane Lock, Enhance Ability, Detect Thoughts, Hold Person, Silence, Misty Step, Darkness, Darkvision, Enthrall-style control, Crown of Madness, and **Eldritch Detonation**.

### 3rd Level
Counterspell, Fear, Hypnotic Pattern, Speak with Dead, Stinking Cloud, Vampiric Touch, and **Eldritch Barrage**.

### 4th Level
Dimension Door, Confusion, Death Ward, Greater Invisibility, Freedom of Movement.

### 5th Level
Hold Monster, Contagion, Cloudkill, Dominate Person.

### 6th Level
**Eldritch Annihilation**.

---

## 7. Custom Spells

### Eldritch Detonation — 2nd Level

- Base damage: 2d12 Force;
- approximately 2m explosion radius;
- base casting range matches Eldritch Blast and scales with Eldritch Spear;
- target rolls both Intelligence and Charisma saves;
- both saves fail: full damage;
- either save succeeds: half damage;
- +1d12 damage per upcast level.

### Eldritch Barrage — 3rd Level

Select one target and automatically fire a sequence of derived Eldritch rays at that same creature. Each ray deals only 1 base Force damage but independently triggers the Eldritch Blast passive pipeline.

| Spell level | Base rays | With Pursuit Blast |
|---|---:|---:|
| 3rd | 8 | 9 |
| 4th | 10 | 11 |
| 5th | 12 | 13 |

### Eldritch Annihilation — 6th-Level Mystic Arcanum

- usable once per long rest;
- does not consume a normal pact slot;
- reduces the caster's current HP to 1;
- ray count = `floor(HP lost / 2)`;
- capped at 12 base rays;
- chooses creatures within 12m regardless of allegiance;
- if Repelling Blast pushes a target outside the 12m boundary, that target receives one follow-up ray;
- every Annihilation ray that hits grants 1 additional temporary HP.

A technical total-ray cap prevents abnormal recursive behavior.

---

## 8. Power Level

Manaweaver is intentionally stronger than a normal vanilla single-class build.

Its power comes from the combination of:

**many independent attack rolls + per-beam control + ability-score debuffs + knockback + healing + temporary HP + resource refunds + death retaliation + revival + action economy.**

v8 limits the three most dangerous loop generators:

1. only one miss-generated bonus action per round;
2. only one successful pact-slot refund per round;
3. only one Mana Heart III revival per combat and three per long rest.

The subclass is still deliberately powerful, but these limits substantially reduce the risk of infinite actions, infinite resources and infinite revival loops.

---

## 9. Version History

| Version | Main changes | Source |
|---|---|---|
| v1 | Static LevelMap six-beam experiment; did not work in Patch 8 testing | [`versions/v1`](versions/v1/) |
| v2 | Script Extender runtime LevelMap; first in-game successful six-beam build | [`versions/v2`](versions/v2/) |
| v3 | Progressive per-beam damage; d14/d16 equal-average approximations | [`versions/v3`](versions/v3/) |
| v4 | Eldritch Blast specialization system; first six custom blast passives and Sorcery Point experiment | [`versions/v4`](versions/v4/) |
| v5 | Rebuilt as the true Manaweaver subclass; Mana Curse / Mana Heart / Mana Mastery progression | [`versions/v5`](versions/v5/) |
| v6 | Independent progression; Pact Boon and vanilla invocation removal; Sorcery Points replaced by pact-slot mechanics | [`versions/v6`](versions/v6/) |
| v7 | Fear Blast, exclusive spell list and three custom spells; shipped with a LOCA offset defect | [`versions/v7`](versions/v7/) |
| **v8** | **Localization binary fix plus action/resource/revival balance limits; current source baseline** | [`versions/v8`](versions/v8/) |

### v1
Started as a simple attempt to make Eldritch Blast gain one additional beam every two levels and reach six beams by level 12. The static LevelMap override did not take effect in Patch 8 testing.

### v2
Moved the LevelMap modification into Script Extender runtime code. This approach was successfully verified in-game and established the technical direction used by later builds.

### v3
Explored different damage dice for individual beams. Because BG3 has no native d14 or d16 dice, `1d12+1` and `1d12+2` were used as equal-average approximations.

### v4
Expanded the project into an Eldritch Blast specialization system and introduced the first custom passive suite: Metamagic Blast, Spell-Eating Blast, Soul-Draining Blast, Pursuit Blast, Weakening Blast and Ultimate Blast.

### v5
Rebuilt the system as an actual Warlock subclass called Manaweaver, with the level 1/5/11 Mana Curse, Mana Heart and Mana Mastery progression.

### v6
Gave Manaweaver a truly independent progression: no Pact Boon and no vanilla Eldritch Invocation selection. The Sorcery Point concept was discarded in favor of Warlock pact-slot mechanics.

### v7
Replaced Metamagic Blast with Fear Blast and added the exclusive spell list, Eldritch Detonation, Eldritch Barrage and Eldritch Annihilation. Its `.loca` writer incorrectly used a 74-byte entry stride, causing shifted/garbled localization in-game.

### v8
Corrected LOCA entries to the proper 70-byte layout, added binary round-trip localization validation, and introduced the three balance limits. This is the current source baseline.

---

## 10. Debugging

v8 Script Extender debug command:

```text
!sr_eb_v8_dump
```

Runtime logs are normally written under:

```text
%LOCALAPPDATA%\Larian Studios\Baldur's Gate 3\Script Extender\Shrink_EldritchSorcerer_Patch8_v8\
```

---

## 11. Known Boundaries

- Development is driven by Patch 8 in-game testing; compatibility with every level-cap, class overhaul, spell overhaul or Script Extender mod is not guaranteed.
- Custom 2nd/3rd-level spell upcast detection in complex multiclass setups still benefits from further in-game calibration.
- v7 is intentionally kept as a historical source snapshot even though its localization build is known to be broken. Use v8 or a later version for actual play.

---

## 12. License

This project is distributed under the repository's **GNU General Public License v3.0 (GPL-3.0)**.
