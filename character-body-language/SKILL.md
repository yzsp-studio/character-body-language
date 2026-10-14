---
name: character-body-language
description: |
  AI 视频角色"全身非言语行为"精准控制专家。将行为心理学、身势学（Kinesics）、
  近距学（Proxemics）、步态分析学和非言语行为学，转化为 AI 视频可理解的身体描述。
  覆盖四大模块：
  1. 体态语言（Posture & Gesture）：开放/封闭/权力/服从/吸引/回避六大姿态组
  2. 空间关系调度（Proxemics）：四级距离区 × 朝向组合 × 镜像/断裂行为
  3. 步态系统（Gait）：身份步态 + 情绪步态 + 状态步态
  4. 无意识微动作（Unconscious Micro-movements）：自我适应动作、物体适应动作、
     自我梳理行为、生理性非自愿动作、情绪泄漏信号
  解决三大核心问题：
  - "两个角色像各拍各的" → 空间关系 + 体态对比
  - "角色站着一动不动像机器人" → 无意识微动作
  - "走路像滑行" → 步态系统
  触发词包括：身体语言、体态、kinesics、空间关系、proxemics、人物站位、
  多人场景、角色关系、权力关系、亲密距离、步态、gait、走路方式、
  无意识动作、微动作、self-adaptor、小动作、习惯动作、紧张动作、fidgeting、
  物体适应、让角色更自然、角色太呆板、角色像机器人、
  body language、posture、gesture、power pose、staging、
  idle animation、unconscious movement、self-grooming。
summary-cn: 角色身体语言系统——体态/空间/步态/微动作四合一
summary-en: Character body language system — posture, proxemics, gait & micro-movements
version: 1.0.0
tags: [Video, Prompt Engineering, Kinesics, Proxemics, Gait, Non-verbal Behavior, Character Animation]
tags-cn: [视频, 角色动画, 身体语言]
trigger-words: [身体语言, 体态, kinesics, 空间关系, proxemics, 人物站位, 多人场景, 角色关系, 权力关系, 亲密距离, 步态, gait, 走路方式, 无意识动作, 微动作, self-adaptor, 小动作, 习惯动作, 紧张动作, fidgeting, 物体适应, 让角色更自然, 角色太呆板, 角色像机器人, body language, posture, gesture, power pose, staging, idle animation, unconscious movement, self-grooming, 镜像行为, 身体朝向, 步态分析, 场面调度]
author: yzsp-ai
repository: https://github.com/yzsp-ai
---


# 角色身体语言系统 — Character Body Language System

让 AI 视频角色拥有完整的身体表达能力：**站怎样、离多远、怎么走、手在干什么**。

## 铁律（嵌入身体语言前必读）

1. **每镜最多 2-3 个微动作**，超过 3 个模型全部忽略
2. **微动作在主动作间隙出现**，不能和主动作同时抢注意力
3. **禁止抽象词**："紧张地动" → 具体写哪个部位、怎么动、多大幅度
4. **物理不冲突**：双手端枪时不能写"搓手"
5. **步态三参数必写**：步幅(cm) + 步频(/min) + 重心高度，缺任何一个 = 滑行
6. **空间距离必须匹配关系**：恋人用社交区距离 = 看起来像陌生人

## 反模式

| 反模式 | 翻车原因 | 正确做法 |
|--------|---------|---------|
| 写 5 个以上微动作 | 模型注意力溢出 | 只保留最符合情绪的 2 个 |
| "角色紧张地站着" | 模型不知道怎么表现"紧张" | "right hand gripping left forearm, weight shifting to left foot every 2s" |
| 步态只写"慢慢走" | 没有物理参数 = 滑行 | "short 40cm shuffling steps at 60/min, leaning 10° forward" |
| 两人空间关系不写距离 | 模型随机放人 | 显式写 "standing 45cm apart, bodies angled 30° toward each other" |
| 微动作和情绪不一致 | 搓手(焦虑) + 微笑(放松) = 混乱 | 所有信号指向同一情绪 |

**核心理念**：人类的身体是永不停歇的广播设备——你的站姿、距离、朝向、步态、
手上的小动作，每一秒都在"广播"你的情绪和人际关系。
AI 角色缺少这些 = 观众读不出角色状态和人物关系。

**与其他 Skill 的关系**：
- `video-prompt-craft` = 有目的的表演（表情/眼神/动作链/运镜）→ 提示词生成
- **本 Skill** = 无目的的存在（体态/空间/微动作/步态）→ 角色真实感
- `voice-performance-layer` = 声音维度（语速/停顿/气息）→ 听觉表演

---

## STEP 0: DIAGNOSE — 角色哪里"不对劲"

| 症状 | 诊断 | 调用模块 |
|------|------|---------|
| 两个角色像各拍各的 | 缺少空间关系 | → 模块B: 空间关系 |
| 看不出谁是老板谁是下属 | 缺少权力体态对比 | → 模块A: 体态 §权力/服从 |
| 角色站着一动不动 | 缺少待机微动作 | → 模块D: 微动作 §待机 |
| 紧张场景角色太镇定 | 缺少焦虑泄漏 | → 模块D: 微动作 §焦虑 |
| 角色走路像滑行 | 缺少步态描述 | → 模块C: 步态 |
| 角色手里有东西但不互动 | 缺少物体适应 | → 模块D: 微动作 §物体 |
| 恋人看起来像陌生人 | 缺少亲密信号 | → 模块A §吸引 + 模块B §亲密区 |
| 情绪转折太突兀 | 缺少过渡泄漏 | → 模块D: §情绪泄漏 |

---

## STEP 1: CONTEXT — 三维定位

### 1a. 角色关系（多人场景）

| 关系类型 | 体态关键词 | 空间关键词 |
|---------|----------|----------|
| 权力不对等 | 展开 vs 收缩 | 占据 vs 退让 |
| 合作/同盟 | 镜像 / 开放 | 并肩 / 同朝向 |
| 对立/敌对 | 正对 / 收紧核心 | 最大安全距离 |
| 亲密/浪漫 | 倾向 / 暴露 | 侵入亲密区 |
| 审讯/操控 | 入侵 + 退缩 | 不对称距离 |

### 1b. 情绪状态（单人/微动作）

| 状态 | 主要泄漏通道 |
|------|-------------|
| 焦虑/紧张 | 手部自我触摸频率↑、搓手、抖腿 |
| 无聊/等待 | 物体把玩、环顾、姿势频繁调整 |
| 思考/专注 | 摸下巴、咬笔、凝视一点不动 |
| 防御/不安 | 交叉双臂、握住自身、退缩 |
| 舒适/放松 | 姿势展开、缓慢梳理 |
| 压抑愤怒 | 攥拳松开循环、咬紧牙关 |

### 1c. 角色身份（影响微动作密度和步态）

| 身份类型 | 微动作特征 | 步态特征 |
|---------|----------|---------|
| 高地位 | 少且克制、占据空间大 | 步幅大、稳定 |
| 低地位 | 多且碎、缩小空间 | 步幅小、紧凑 |
| 军人 | 几乎无、偶尔喉结吞咽 | 精确均匀、手臂刚性摆动 |
| 儿童 | 幅度大、注意力跳跃 | 不规则弹跳 |

---

## 模块 A: 体态语言系统

六大姿态组，详细参数见 `references/posture-catalog.md`。

### ① 开放姿态 — 信任/自信
`torso facing directly, chest open, arms loose, palms visible, feet shoulder-width`

### ② 封闭姿态 — 防御/拒绝
`torso angled 30° away, arms crossed tightly, legs crossed, chin lowered`

### ③ 权力姿态 — 支配/控制
`spine erect, chest expanded, palms planted on desk, feet wider than shoulders, chin raised 10°`

### ④ 服从姿态 — 顺从/自卑
`upper body leaning forward 15°, shoulders rounded, hands clasped on lap, head bowed`

### ⑤ 吸引姿态 — 兴趣/好感
`torso leaning 10° toward the other, wrist showing inner forearm, feet pointing at partner`

### ⑥ 回避姿态 — 排斥/想离开
`torso leaning back 15°, arm creating barrier, lead foot pointing toward door`

---

## 模块 B: 空间关系调度

### 四级距离区

| 距离区 | 范围 | 关系 |
|-------|------|------|
| 亲密区 | 0-45cm | 恋人/亲子 |
| 个人区 | 45-120cm | 好友/同事 |
| 社交区 | 120-360cm | 一般社交 |
| 公共区 | 360cm+ | 陌生人 |

**冲突=戏剧性**：距离与关系不匹配时产生张力。

### 朝向组合

| 组合 | 信号 |
|------|------|
| 正对 (0°) | 对抗/亲密 |
| 平行 (同向) | 同盟/合作 |
| L型 (90°) | 轻松对话 |
| 背对背 (180°) | 信任/分离 |

### 镜像与断裂

- **镜像**（亲近）：两人无意识复制对方姿态
- **断裂**（冲突）：一方开放另一方封闭，脚尖不再对齐

---

## 模块 C: 步态系统

详细参数见 `references/gait-catalog.md`。

### 身份步态

| 身份 | Prompt 片段 |
|------|------------|
| 军人 | `precise 75cm strides at 120/min, arms in rigid arcs, chin level` |
| 模特 | `feet crossing center line, hips swaying 5cm, chin 5° up` |
| 老年人 | `short 40cm shuffling steps, leaning 10° forward` |
| 儿童 | `erratic bouncy steps, arms swinging wide, head turning everywhere` |

### 情绪步态

| 情绪 | Prompt 片段 |
|------|------------|
| 自信 | `stride lengthening to 80cm, weight high, slight bounce` |
| 焦虑 | `hurried 50cm steps at 140/min, arms pressed close` |
| 悲伤 | `dragging 35cm steps, feet barely clearing ground, shoulders slumped` |
| 愤怒 | `heavy stomping 85cm strides, each footfall audible` |
| 偷偷摸摸 | `toe-first 25cm steps, body crouching, arms still` |

### 状态步态

| 状态 | Prompt 片段 |
|------|------------|
| 受伤跛行 | `right leg shortened stance, body lurching left each step` |
| 醉酒 | `weaving path, stride 30-80cm varying, swaying 10cm side to side` |
| 极度疲劳 | `shuffling with frequent 2s pauses, hands bracing knees` |
| 高跟鞋 | `hips swaying 8cm laterally, 50cm restricted strides, knees slightly bent` |

---

## 模块 D: 无意识微动作系统

详细查找表见 `references/micro-movement-catalog.md`。

**核心原理**：人类身体从不完全静止。即使"站着不动"也在调整重心、摸鼻子、舔嘴唇。
AI角色缺少这些 = 停机的机器人。

### D1: 自我适应动作（Self-Adaptors）

| 触摸区域 | 情绪 | 描述模板 |
|---------|------|---------|
| 额头/太阳穴 | 认知压力 | 指尖按压太阳穴画小圆 |
| 鼻子/嘴唇 | 犹豫/说谎抑制 | 食指轻触鼻尖0.3s后收回 |
| 下巴 | 思考/评估 | 拇指食指捏下巴 |
| 后颈 | 尴尬 | 右手掌覆盖后颈摩擦2-3次 |
| 手-搓手 | 焦虑 | 双手掌心交替搓动 |
| 手-握拳松开 | 压抑愤怒 | 拳头握紧1s缓慢松开循环 |
| 腿-抖腿 | 焦虑/不耐烦 | 前脚掌支撑，脚跟3Hz频率轻弹 |

### D2: 自我梳理（Self-Grooming）

| 行为 | 情绪 | 描述模板 |
|------|------|---------|
| 捋头发 | 缓解紧张 | 手指从耳后插入发际将发束拨至肩前 |
| 整衣领 | 社交准备 | 食指中指夹衣领边缘向外拉0.5cm松开 |
| 舔嘴唇 | 紧张/准备说话 | 舌尖沿上唇弧线滑过 |
| 咬嘴唇 | 犹豫/强忍 | 下唇被上齿轻咬0.5-1s |

### D3: 物体适应动作（Object-Adaptors）

| 物体 | 焦虑模式 | 无聊模式 | 思考模式 |
|------|---------|---------|---------|
| 笔 | 快速点击笔帽 | 手指间翻转旋转 | 笔尖抵住下唇不动 |
| 杯子 | 双手紧握，拇指摩擦杯沿 | 单手转杯画圆 | 凝视杯中不喝 |
| 手机 | 反复翻转，滑动黑屏 | 弹手机壳边缘 | 面朝下放桌又拿起 |
| 戒指 | 反复旋转 | 摘下套上 | 拇指扣内侧不动 |

### D4: 生理性非自愿动作

| 动作 | 触发 | 描述 |
|------|------|------|
| 喉结滚动 | 紧张/干燥 | 喉结上升0.5cm后缓慢回落 |
| 眨眼加速 | 焦虑 | 从15次/min升至25次/min |
| 手指微颤 | 恐惧/肾上腺素 | 指端0.5mm幅度微颤 |
| 汗液微光 | 紧张 | 鼻尖额头细密汗珠反光 |
| 肌肉微跳 | 疲劳/紧张 | 眼皮或嘴角不规则抽搐 |

### D5: 情绪泄漏信号

角色**试图掩饰情绪**时的"泄漏"。

| 掩饰 | 泄漏信号 |
|------|---------|
| 假装镇定 | 呼吸刻意但不均匀，握物指节发白 |
| 假笑 | 嘴角上扬但眼周无鱼尾纹 |
| 假装不在意 | 动作刻意慢但杯沿轻微晃动 |
| 压抑哭泣 | 下巴颤抖、频繁吞咽 |
| 压抑愤怒 | 咬肌隆起、指甲嵌入掌心 |

---

## STEP 2: COMPOSE — 嵌入模板

### 多人场景
```
[场景],
角色A: [身份], [体态组], [朝向], [位置]
角色B: [身份], [体态组], [朝向], [位置]
空间关系: [距离区] + [朝向组合] + [镜像/断裂],
[如有行走] 步态: [身份 × 情绪修正],
```

### 单人+微动作
```
[主要动作],
同时/期间,
[微动作1: 自我适应/物体适应],
[微动作2: 生理性/梳理行为],
```

### 嵌入原则
1. 每个镜头最多 2-3 个微动作（不过载）
2. 微动作在主动作间隙出现（时间错位）
3. 主动作占描述 70%，微动作占 30%
4. 物理不冲突（双手拿东西时不能搓手）
5. 情绪方向一致

---

## STEP 3: SELF-CHECK

- [ ] 角色间距离匹配关系类型
- [ ] 体态组合正确传递关系
- [ ] 脚尖朝向与意图一致
- [ ] 步态三参数齐全（步幅/步频/重心）
- [ ] 微动作数量 ≤ 3
- [ ] 微动作与主动作无物理冲突
- [ ] 每个微动作有具体部位+方式+频率
- [ ] 没有抽象词（"紧张地动"→ 具体哪里怎么动）

---

## STEP 4: PRESENT & ITERATE

输出嵌入了身体语言描述的完整提示词。

反馈处理：
- "关系不明显" → 增大体态对比+加脚尖方向
- "动作太多太碎" → 减到1-2个，增加持续时间
- "动作太夸张" → 降低幅度（cm→mm）
- 更多选项 → 加载 references 目录下的详细目录
