# v8 — Current / 最新版

## 中文
v8 是当前最新版，重点修复 v7 的本地化损坏并加入三条平衡限制。

### 修复
- 修正 `.loca` 二进制生成器：条目固定长度应为70字节（64-byte Key + 2-byte Version + 4-byte Length），而非 v7 错误使用的74字节。
- 构建流程增加 LOCA 二进制反向解析与 XML 逐条比对，避免名称、描述串位和乱码再次出现。
- 清理已废弃的术法魔爆本地化条目。

### 平衡限制
- **魔能精通：** 魔能爆 Miss 获得附赠动作改为每战斗轮最多1次。
- **噬法魔爆：** 击杀返还契约法术位改为每战斗轮最多1次；若法术位已满则不消耗本轮返还额度。
- **魔能之心III：** 复活每场战斗最多1次、每次长休之间最多3次。达到上限后死亡魔爆仍会正常释放，只是不再复活。

v7 的恐惧魔爆、专属法表、魔能爆裂、魔爆倾泻、魔能湮灭以及 v5/v6 的完整魔能术士职业体系均保留。

调试命令：`!sr_eb_v8_dump`

## English
v8 is the current release. It focuses on fixing the v7 localization corruption and adding three balance limits.

### Fixes
- Corrects the binary `.loca` writer: each entry is 70 bytes (64-byte key + 2-byte version + 4-byte length), not the incorrect 74-byte stride used by v7.
- Adds a binary LOCA round-trip validation step that compares every decoded entry against the XML source, preventing shifted names, descriptions and garbled localization.
- Removes obsolete Metamagic Blast localization entries.

### Balance limits
- **Mana Mastery:** bonus action gained from an Eldritch Blast miss is limited to once per combat round.
- **Spell-Eating Blast:** pact-slot restoration from kills is limited to once per combat round; a kill made while pact slots are already full does not consume the round's refund quota.
- **Mana Heart III:** revival is limited to once per combat and three times per long rest. The death barrage still triggers after the revival quota is exhausted; only the revival is blocked.

All major v7 mechanics remain: Fear Blast, the exclusive Manaweaver spell list, Eldritch Detonation, Eldritch Barrage, Eldritch Annihilation, and the complete Manaweaver progression introduced in v5/v6.

Debug command: `!sr_eb_v8_dump`

## Source archive / 源码归档
This source snapshot is split into three `.tar.xz` parts. Generated binary `.loca` files are omitted; editable `.loca.xml` files are retained.

```bash
cat Manaweaver_v8_source.tar.xz.part-* > Manaweaver_v8_source.tar.xz
tar -xJf Manaweaver_v8_source.tar.xz
```
