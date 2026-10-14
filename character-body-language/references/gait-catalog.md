# 步态完整参数表 — Gait Catalog

步态六维描述框架：**步幅 × 步频 × 重心 × 手臂 × 头部 × 脊椎**

---

## 一、基准正常步态参数

| 参数 | 男性成年 | 女性成年 | 单位 |
|------|---------|---------|------|
| 步幅 | 70-80cm | 60-70cm | cm/步 |
| 步频 | 100-120 | 110-130 | 步/min |
| 重心高度 | 身高 55% | 身高 55% | 比例 |
| 重心侧移 | ±2-3cm | ±3-5cm | cm |
| 手臂摆幅 | 前 15° 后 10° | 前 12° 后 8° | 角度 |
| 头部 | 水平前视 | 水平前视 | — |
| 脊椎 | 自然 S 曲线 | 自然 S 曲线 | — |

---

## 二、身份步态详表

### 军人/警察

| 维度 | 参数 | 描述 |
|------|------|------|
| 步幅 | 75cm ±2cm | 高度均匀，机械般精确 |
| 步频 | 120/min（正步可达 140） | 节奏像节拍器 |
| 重心 | 高位居中，几乎无侧移 | 稳定如行走的柱子 |
| 手臂 | 前摆 90° 后摆 45°（正步） / 紧贴体侧 | 严格规范 |
| 头部 | 正前方，眼神水平 | 目不斜视 |
| 脊椎 | 笔直，微微后仰 | 挺胸收腹 |
| Prompt | `rigid 75cm strides at 120/min cadence, arms swinging in precise 90° forward arcs, spine ramrod straight, chin level, eyes fixed dead ahead, zero lateral sway` |

### 模特

| 维度 | 参数 | 描述 |
|------|------|------|
| 步幅 | 55-65cm | 受限于高跟 |
| 步频 | 100-110/min | 稍慢，留出展示时间 |
| 重心 | 高位，髋部主导侧移 | 标志性的猫步 |
| 手臂 | 自然下垂，微贴身体 | 不干扰视觉焦点 |
| 头部 | 微仰 5°，目光平或略向下 | 高冷感 |
| 脊椎 | 笔直，骨盆前倾 | 凸显曲线 |
| 特征 | 脚交叉中线（猫步） | 步幅窄于肩宽 |
| Prompt | `feet crossing the body's center line with each step (catwalk), hips swaying 5-8cm laterally, chin 5° up, gaze directed slightly downward through lashes, arms floating at sides with relaxed wrists` |

### 老年人

| 维度 | 参数 | 描述 |
|------|------|------|
| 步幅 | 35-50cm | 明显短于青年 |
| 步频 | 80-100/min | 缓慢但不一定不规则 |
| 重心 | 前倾 8-12° | 补偿肌力下降 |
| 手臂 | 摆幅缩小至 5°，可能需辅助 | 常持拐杖或扶物 |
| 头部 | 前伸 | 颈椎前曲 |
| 脊椎 | 胸椎后凸增大 | 驼背 |
| 特征 | 脚不完全离地（拖步声） | 鞋底摩擦地面 |
| Prompt | `short 40cm shuffling steps, feet barely clearing the ground with audible friction, upper body tilted 10° forward, arms barely swinging, hand trailing the wall for balance, thoracic spine curved into a gentle hunch` |

### 儿童（4-8岁）

| 维度 | 参数 | 描述 |
|------|------|------|
| 步幅 | 30-45cm | 腿短 |
| 步频 | 130-160/min | 极快 |
| 重心 | 高且不稳 | 头占比大 |
| 手臂 | 大幅无规则摆动 | 有时举过头顶 |
| 头部 | 频繁转动 | 对一切好奇 |
| 脊椎 | 略后仰（腹部突出） | 正常儿童姿态 |
| 特征 | 随时可能变成跑/跳/蹦 | 不可预测 |
| Prompt | `erratic bouncy 35cm steps at 150/min, arms swinging wide and asymmetrical, head swiveling left and right with every new stimulus, suddenly breaking into a 3-step skip then resuming walking, belly protruding slightly forward` |

### 醉酒者

| 维度 | 参数 | 描述 |
|------|------|------|
| 步幅 | 30-80cm（不规则） | 时大时小 |
| 步频 | 70-110/min（不规则） | 节奏混乱 |
| 重心 | 剧烈侧摆 ±10-15cm | 险些倒下 |
| 手臂 | 伸出寻求平衡 | 或扶墙 |
| 头部 | 滞后于身体转向 | 脖子松弛 |
| 脊椎 | 过度弯曲或过度后仰 | 失去正常张力 |
| 路径 | 偏离直线 ±30cm | 锯齿形前进 |
| Prompt | `weaving path with stride length varying wildly between 30-80cm, center of mass swaying ±12cm laterally, one arm reaching for the wall, head lagging behind body direction changes by 0.5s, occasionally stopping to regain balance with a wide-stance plant` |

---

## 三、情绪步态修正表

在身份步态基础上叠加情绪修正。

| 情绪 | 步幅修正 | 步频修正 | 重心修正 | 附加特征 |
|------|---------|---------|---------|---------|
| 自信 | +15% | 不变 | 上移 2cm | 步伐有弹性，落地有力 |
| 高兴 | +10% | +10% | 上移 | 步态轻盈，偶有小跳步 |
| 焦虑 | -20% | +25% | 前移 | 快速碎步，手臂紧贴 |
| 悲伤 | -30% | -20% | 下沉 | 拖步，肩下垂 |
| 愤怒 | +20% | +10% | 下沉，前冲 | 重踏步，拳头握紧 |
| 恐惧 | 极端化（极短或极长） | 极端化 | 不稳定 | 回头，路径不直 |
| 偷偷摸摸 | -50% | -30% | 极低 | 脚尖先落地，无声 |
| 得意 | +10% | 不变 | 高位后仰 | 摇摆步态，手插口袋 |

---

## 四、状态步态详表

### 跛行（腿伤）

```
受伤腿（右腿）：
- 着地时间缩短至正常的 40%（疼痛回避）
- 膝盖不完全伸直，保持 15° 弯曲
- 落地时身体向左侧倾斜 8°（向健侧逃避）

健康腿（左腿）：
- 着地时间延长至正常的 160%（代偿）
- 步幅增大 20%（补偿对侧缩短）
- 左肩在右脚落地时下沉 3cm（重力补偿）

Prompt: limping with right leg — right foot barely touching ground for 0.2s
before weight lurches to the left, body tilting 8° leftward, left leg
overstepping to 85cm to compensate, right knee held at 15° bend,
left shoulder dipping 3cm each time the right foot strikes.
```

### 负重行走

```
前倾角度：与负重成正比（10kg→5°, 20kg→10°, 30kg→15°）
步幅：减少 20-30%
步频：降低 15-25%
脚落地方式：全脚掌着地（增大接触面积）
手部：双手固定在负重物上

Prompt: carrying a 20kg box — torso tilted 10° forward, short 50cm steps
at 90/min, flat-footed stomps for stability, both arms locked around the box,
forearms trembling under sustained load, chin tucked to see over the top edge.
```

### 高跟鞋行走

```
与平底的区别：
- 踝关节活动范围限制 50%
- 膝关节始终保持 5-10° 弯曲（不完全伸直）
- 髋部侧移增大 50-80%（代偿平衡）
- 步幅缩短 15-25%
- 落地顺序改变：前脚掌→脚跟（颠倒正常顺序）

Prompt: walking in 8cm heels — forefoot striking first, knees never fully
extending, hips compensating with 8cm lateral sway per step, stride restricted
to 50cm, each step placed carefully along a narrow line, calves visibly taut.
```

### 在冰面/湿滑地面

```
特征：
- 步幅极短（20-30cm）
- 脚近乎垂直落地（不前推）
- 手臂展开至身体两侧（平衡）
- 膝盖弯曲 20-30°（降低重心）
- 速度极慢

Prompt: tiny 25cm steps on icy ground, feet lowering vertically with zero
forward slide, knees bent 25°, arms extended to the sides like a tightrope
walker, weight shifting extremely slowly between feet over 1.5s per step.
```
