# 体态语言完整查找表 — Posture Catalog

按关系场景 × 姿态组合交叉索引。

---

## 一、权力对比场景组合

### 1.1 上级 vs 下级（办公室/会议）

| 上级体态 | 下级体态 | 关系强度 | 场景 |
|---------|---------|---------|------|
| 双手撑桌、肩展开、站立 | 坐椅前沿、手握膝盖、肩缩 | 强 | 训斥 |
| 后仰椅背、双手交叉脑后 | 前倾笔记、频繁点头 | 中 | 汇报 |
| 站立背手、缓步踱步 | 坐定不动、目光追随 | 中 | 审视 |
| 坐着、单手指向文件 | 站立弯腰看文件 | 弱 | 讨论 |

**Prompt 组合示例（训斥场景）**：
```
Boss: standing behind desk, palms flat on surface fingers spread, shoulders
expanded to full width of the desk, spine rigid, chin elevated 10° looking
down the nose ridge.
Employee: perched on the front 1/3 of the chair, hands gripping kneecaps,
shoulders rounded inward reducing body width by 15%, gaze locked on the
desk surface between the boss's hands.
Spatial: 130cm across desk, face-to-face orientation, height differential
of 40cm (standing vs sitting), boss leaning forward 5° reducing gap to 110cm.
```

### 1.2 审讯 / 心理操控

| 审讯者 | 被审讯者 | 策略 |
|-------|---------|------|
| 缓慢围绕走动、时而停在身后 | 固定坐姿、只能转头追踪 | 空间支配 |
| 突然前倾至 50cm | 身体后仰贴椅背 | 距离入侵 |
| 双手插口袋、放松体态 | 手握紧椅子扶手 | 反差压力 |
| 坐桌角上（高于对方） | 坐椅子（低于对方） | 高度支配 |

---

## 二、亲密关系场景组合

### 2.1 恋人/密友

| 阶段 | A 的体态 | B 的体态 | 距离 | 特征信号 |
|------|---------|---------|------|---------|
| 初期暧昧 | 部分镜像、脚尖指向B | 头侧倾、露颈线 | 70-90cm | 延迟镜像（A动作→1.5s后B跟随） |
| 热恋 | 身体倾向B 15°、触摸频繁 | 完全镜像、靠近A | 15-30cm | 同步呼吸、持续身体接触 |
| 冷战 | 脚尖指向出口、身体回避 | 双臂交叉、头转45° | 100-150cm | 镜像断裂、朝向不一致 |
| 和好 | 一只脚朝B、另一只朝出口（矛盾） | 身体微微转向A | 80-100cm | 不完全镜像恢复中 |

### 2.2 亲子

| 场景 | 父/母体态 | 孩子体态 | 空间特征 |
|------|---------|---------|---------|
| 保护 | 身体朝外面向威胁源 | 藏在父母身后抓衣角 | 亲密区、孩子被遮挡 |
| 教导 | 蹲下至孩子高度 | 仰头看、身体前倾 | 亲密区、减少高度差 |
| 责备 | 站立、双手叉腰 | 低头、双手背后 | 社交区边缘、高度差最大 |

---

## 三、对抗/冲突场景组合

### 3.1 言语对抗（争吵但不动手）

| A 体态 | B 体态 | 升级信号 |
|-------|-------|---------|
| 手指指向B | 双手张开表示无辜 | 指向=攻击性升级 |
| 前倾入侵个人区 | 后退半步但不转身 | 距离缩小=危险信号 |
| 下巴前伸、颈部暴露 | 下巴内收、保护喉咙 | 颈部暴露=挑衅 |
| 重心前移至前脚掌 | 重心后移至后脚跟 | 重心=准备攻击or撤退 |

### 3.2 物理对抗前（即将动手）

| 攻击者 | 防御者 | 临界信号 |
|-------|-------|---------|
| 脱外套/卷袖子 | 后退、双手抬至胸前 | 脱衣=去除约束 |
| 侧身（减小目标面积） | 正面面对（不知所措） | 侧身=战斗准备 |
| 重心极低、膝盖微弯 | 身体僵直 | 降低重心=发力准备 |

---

## 四、社交场景组合

### 4.1 初次见面

| 场景 | 体态 A | 体态 B | 空间 |
|------|-------|-------|------|
| 商务握手 | 正面、右手前伸 | 正面、右手前伸 | 个人区边缘(100cm) |
| 社交派对 | 60°开放角度、饮品在远离B的手中 | 类似角度 | L型站位(90°) |
| 不想交谈 | 身体45°偏转、脚尖朝外 | — | 社交区(200cm+) |

### 4.2 群体中的地位暗示

| 角色 | 体态 | 空间行为 |
|------|------|---------|
| 群体领袖 | 占据中心位、姿态最展开 | 他人围绕其旋转 |
| 亲信/副手 | 靠近领袖、部分镜像 | 站在领袖侧后方 |
| 边缘人 | 姿态封闭、面向圈外 | 站在圈的外层 |
| 挑战者 | 与领袖对称的展开姿态 | 和领袖保持正对 |

---

## 五、高级组合技法

### 5.1 体态矛盾（角色内心冲突）

当角色的上半身和下半身"说不同的话"时，暗示内心矛盾。

| 上半身 | 下半身 | 含义 | Prompt 片段 |
|-------|-------|------|------------|
| 微笑、开放 | 脚尖指向出口 | 礼貌但想走 | `smiling and nodding, but lead foot angled 30° toward the exit` |
| 交叉双臂（防御） | 脚尖指向对方 | 抗拒但想留下 | `arms crossed defensively, yet both feet planted pointing at the other` |
| 前倾（兴趣） | 重心在后脚（准备后退） | 好奇但害怕 | `torso leaning forward with curiosity, weight shifting to the back foot` |

### 5.2 动态关系转折

关系在一个镜头内发生变化的体态描述：

**从合作到对立**：
```
Initially mirroring each other's posture at 45° orientation (collaborative);
at the 2s mark, A's shoulders square up to face B directly (0° confrontation),
B responds by leaning back 10° and crossing arms within 0.5s (defensive shift).
Feet remain unchanged — B's toes still point at A, revealing unresolved
attachment beneath the defensive posture.
```

**从陌生到亲密**：
```
Starting at 150cm social distance, both bodies angled 90° (L-formation);
across 5s, A shifts weight toward B reducing angle to 45°,
B mirrors the lean 1s later (delayed mirror),
distance closes to 80cm, heads tilt toward each other 5° simultaneously.
```
