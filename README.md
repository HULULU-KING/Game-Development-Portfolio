# HULULU · 游戏开发作品集

**Unity 客户端开发 / Gameplay / UI 框架与工具**

围绕自研 UI 框架、输入层、Gameplay 架构、角色动作和移动端接入的两个 Unity 项目。通过可复用模块组织输入、运动、检测、动画与玩法，并为状态切换和边界行为建立验证。

`Unity 2022.3` · `C#` · `Playables` · `Humanoid IK` · `UGUI` · `Input System` · `Addressables`

## 项目

| 项目 | 核心内容 | 技术重点 |
| :--- | :--- | :--- |
| **[TrainingGround →](projects/training-ground.md)** | 3D 动作玩法原型：二段跳、攀爬、三连击、旋风 | 固定步控制、动作时序、接触 IK、技能判定 |
| **[LostHeart →](projects/lost-heart.md)** | 本地双角色合作探索原型：分屏、提灯、怪物与虫群 | 输入分工、玩法 AI、页面框架、UGUI 工具 |

## 项目画面

| LostHeart · 双角色探索 | TrainingGround · 移动端攀爬 |
| :---: | :---: |
| [![LostHeart 双角色与提灯场景](media/lostheart-duo-scene.png)](projects/lost-heart.md) | [![TrainingGround 移动端树干攀爬](media/training-mobile-climb.jpg)](projects/training-ground.md) |

*开发阶段的实际运行截图，点击图片查看对应项目。*

## 重点能力

- **自研 UI 框架与组件**：PageManager 可接入多层页面和页内面板，为打开、关闭、页面切换和面板切换提供统一入口、细分接口及页面生命周期接口，并允许各类切换插入动画；开发 Stencil 并集 Mask 与可控四方向导航。
- **Input System 输入层**：通过输入快照解耦设备采样与玩法逻辑，支持键鼠、手柄和触控接入、本地双人输入分配、运行时改键及配置快照回滚。
- **Gameplay 对象与检测架构**：稳定逻辑根与模型、挂点、移动体、攻击体、Hitbox 分层；按用途选择实体碰撞、SphereCast、注册表对点检测和 NonAlloc Overlap 主动查询。
- **交互与战斗数据流**：以 `WeaponItem.owner` 统一武器归属，完成事务式拾取、主副手与玩家交换；以 `HitData + IHitReceiver` 解耦攻击者和受击对象，并按接收器完成单次命中去重。
- **角色动作模块**：封装固定步长运动模块并以 UPM 包复用；使用 Playables 与数据配置组织动作混合、打断、三段连击和命中窗口。
- **攀爬与移动端**：通过手脚接触约束和 IK 实现上下攀爬、绕树及半径适配；完成多点触控、浮动摇杆、拖拽定向施法、移动纹理处理及 Android 测试包导出。

## 技术拆解

| 阅读入口 | 关注的问题 |
| :--- | :--- |
| [角色控制与动作时序](notes/character-and-combat.md) | 渲染帧输入如何交给固定步？如何让动作姿态与命中窗口对齐？ |
| [Gameplay 对象、检测与战斗架构](notes/gameplay-architecture.md) | 为什么区分四类检测？交互、武器、命中、AI 和动态光照如何协作？ |
| [PageManager 页面框架](notes/page-framework.md) | 如何分离页面调度、生命周期、过渡动画和设置业务？ |
| [验证记录与工程边界](notes/validation.md) | 已有检查覆盖什么？有哪些尚未完成的内容？ |

## 关于本作品集

作者：**[HULULU-KING](https://github.com/HULULU-KING)**。内容重点为程序实现、系统设计与工程组织。两项目共享部分基础模块，各自展示不同的玩法与技术侧重。

本仓库公开项目介绍、技术拆解和精选运行截图，完整工程源码单独管理，LostHeart 保持私有。项目处于原型开发阶段；当前展示不包含可下载试玩包或完整操作录像。

**模型制作分工**：TrainingGround 中的模型由另一位团队成员制作；LostHeart 中的模型均由作者本人建模。模型制作贡献与程序实现分别说明。

*内容核对：2026-09-16。*
