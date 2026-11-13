<p align="center"><b>Honor Duo One</b><br>荣耀 MagicOS 状态栏三合一 · 主打胶囊形态</p>

<p align="center">
  <a href="https://github.com/Xposed-Modules-Repo/io.github.honorduoone/releases/latest"><b>下载最新版</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/honorduoone/honorduoone">源码与更新日志</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/honorduoone/honorduoone/issues">问题反馈</a>
</p>

<img src="https://cdn.jsdelivr.net/gh/honorduoone/honorduoone@main/docs/images/statusbar.png" width="100%" alt="状态栏实拍：胶囊接管 Wi-Fi、信号与电池">

荣耀 MagicOS 状态栏的三合一模块，**主打胶囊形态**：把 Wi-Fi、移动信号、电池收进一枚贴合状态栏高度的胶囊里，外形与系统灵动胶囊同族，展开动画里也不突兀。圆环与双排信号作为可选排布保留。

## 为什么主打胶囊

- **与系统同族的外形**：胶囊外形（圆角矩形 + 均匀描边）与 MagicOS 灵动胶囊、控制中心控件属于同一套视觉语言，下拉时不会出现「自定义图标」的割裂感。
- **三槽分区**：上、中、下三个槽位，中部最多放 3 件并按三等分居中排布；信号、Wi-Fi、电量各归其位，不用为了塞下内容缩小字号。
- **单组件双通道箭头**：一枚流量箭头组件内含两组上下行三角，左半移动数据、右半 Wi-Fi，未连接的一侧画灰占位，横向空间只占一份。
- **高度自适应**：胶囊整体高度跟随状态栏行高，不靠缩放凑尺寸，不同机型上描边粗细与留白比例一致。
- **灵动胶囊避让**：灵动胶囊展开时按屏幕物理坐标做碰撞检测，只让被遮挡的组件让位，其余保持原位。

## 可选排布

| 排布 | 形态 | 适合 |
| :--- | :--- | :--- |
| **胶囊**（默认） | 圆角胶囊 + 三槽分区 | 想要与系统风格统一、信息集中 |
| **圆环** | 电池环 + 环内内容 + 环侧 Wi-Fi/信号 | 喜欢环形仪表感，可开下拉形变 |
| **双排信号** | 主卡信号柱 + 副卡圆点 | 双卡用户，需要分别看清两张卡的格数与制式 |

圆环/胶囊与双排信号互斥，切换时会提示并自动关闭另一个。

## 其它特性

- **可放置组件**：电量数字、Wi-Fi 弧、移动信号（卡一/卡二可拆）、网络制式、充电闪电、功率、温度、帧率、时钟等均可独立放置或交还系统。
- **双卡停用显示**：在系统设置里停用一张卡后，对应那一排改用未点亮点的轨道色，位置与行高不变，不显示网络制式，也不会被另一张卡的信号带亮。
- **通知中心天气**：在通知中心日期行末尾显示实时天气与气温，支持文字/图标/图标加文字三种样式，点击日期行可直接打开系统天气应用。
- **鸿蒙堆叠信号**：内置 [StackedSignal_5G](https://www.coolapk.com/feed/74608300?s=NTAxYmJmN2QyZDUxYzFnNmFlZGRjYmJ6a1662) 的图标与判定逻辑，开启后信号图标改由这套堆叠资源绘制，其余自带绘制整体停用（需重启系统界面）。
- **智能防烧屏**：OLED 屏幕的 30 秒 3×3 离散网格微移位，边界安全钳制，开销极低。
- **息屏交接可切换**：默认在息屏（AOD）时把整行交还宿主、亮屏瞬间切回三合一；可在「功能开关」里关闭，让息屏也保持本模块状态栏（切换感消失，代价是息屏下没有电池电量图标，关闭前会提示）。
- **时钟按需接管**：秒/日期/星期/农历/天气全关时完全不碰原生时钟。

## 安装与要求

| 项目 | 说明 |
| :--- | :--- |
| **系统** | 荣耀 MagicOS |
| **Android** | 10 及以上（API 29+） |
| **框架** | 支持 libxposed **API 102** 的 LSPosed |
| **作用域** | 系统界面（`com.android.systemui`） |

1. 到 [Releases](https://github.com/Xposed-Modules-Repo/io.github.honorduoone/releases) 下载最新版 APK。
2. 打开 LSPosed 管理器，启用 **Honor Duo One**，并在作用域里勾选**系统界面**（`com.android.systemui`）。
3. 重启系统界面或重启手机生效。

## 更新节奏

这个项目更新不频繁，只有周末有空处理。平时的 bug 与想法会攒到周末一起做，着急的可以在 [Issues](https://github.com/honorduoone/honorduoone/issues) 里留言。

## 致谢与来源

本模块建立在四个上游项目与一份图标资源之上，逐项写明作者、许可证与具体用途。源码里保留了每一层的版权声明。

**1. [yixing233/HyperDuo](https://github.com/yixing233/HyperDuo)** — 作者 **yixing233**，GPL-3.0，最早的仿 iPhone「Duo」三合一状态栏实现。

- 应用层最底层版权署名的来源；
- 三合一字形的设计空间（120×120 画布）与基础几何；
- 项目结构与 LSPosed 模块骨架。

**2. [odomu/HonorDuo](https://github.com/odomu/HonorDuo)** — 作者 **odomu**，GPL-3.0，HyperDuo 的 MagicOS 适配分支，本项目的直接上游。

- 三合一渲染引擎：`TrioRenderer`、`TrioGeometry`、`TrioZones`；
- 双卡与 Wi-Fi 的状态采样框架（`TrioState`，本项目重写了停用判定与借数链）；
- 液态玻璃设置界面、三分类 Tab 与预览抽屉；
- 作用域跟踪 `ScopeTracker`（对齐上游 1.0.5）；
- `SystemBarHook` 的部分修复（含上游提交 `7489aa8`）。

**3. [nisu123f/HonorDuoBar](https://github.com/nisu123f/HonorDuoBar)** — 作者 **nisu123f**，AGPL-3.0，圆环形态的完整实现。

- 圆环排布：下拉形变、Wi-Fi 弧档位、呼吸填充、蓝牙电量、5G 回退；
- 面板展开时交还原生图标的思路（参考其 1.1.3，本项目改为逐 View 隐藏与释放）；
- 控制中心音量条长按弹荣耀媒体输出弹窗（移植自 1.1.3）；
- 字形裁切修复（1.3.3）：字形始终按设定尺寸绘制。
- 绘制细节修复（1.3.4）：电量弧按圆头端点的可见弧长补偿，防烧屏微移时父容器裁剪判定留出位移余量。

**4. [coderstory/HonorHook](https://github.com/coderstory/HonorHook)** — 作者 **coderstory**，AGPL-3.0，荣耀系 LSPosed 模块。

- 液态玻璃卡片的视觉样式与配色基线；
- 状态栏与通知栏图标替换的 Hook 思路（1.0.1 起并入）；
- 表驱动的挂载点组织方式。

**5. StackedSignal_5G** — 酷安原帖，作者见原帖。

- 鸿蒙堆叠信号的 86 张图标资源与「按信号强度 + 双卡组合选图」的判定逻辑；
- 1.1.11 起 1:1 移植进本模块；
- 出处：<https://www.coolapk.com/feed/74608300?s=NTAxYmJmN2QyZDUxYzFnNmFlZGRjYmJ6a1662>

**框架与依赖**

| 项目 / 作者 | 许可证 | 用途 |
| :--- | :--- | :--- |
| [LSPosed](https://github.com/LSPosed/LSPosed) — LSPosed 开发组 | GPL-3.0 | 模块运行框架 |
| [libxposed](https://github.com/libxposed) — libxposed 团队 | Apache-2.0 | API 102 模块接口 |
| [Miuix](https://github.com/compose-miuix-ui/miuix) — YuKongA 等 | Apache-2.0 | Compose 界面组件库，设置页控件基于它 |
| AndroidX / Jetpack Compose — Google | Apache-2.0 | 基础 UI 与生命周期 |
| [Kotlin](https://kotlinlang.org) — JetBrains | Apache-2.0 | 开发语言与协程 |

如发现署名遗漏或错误，可在 [Issues](https://github.com/honorduoone/honorduoone/issues) 指出，会尽快更正。

## 许可

本项目沿用上游的 **GPL-3.0**，二次修改与再分发请同样开源，并保留上游署名。源码与许可证全文见 [honorduoone/honorduoone](https://github.com/honorduoone/honorduoone)。
