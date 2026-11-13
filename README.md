<p align="center"><b>Honor Duo One</b><br>荣耀 MagicOS 状态栏三合一</p>

<p align="center">
  <a href="https://github.com/Xposed-Modules-Repo/io.github.honorduoone/releases/latest"><b>下载最新版</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/honorduoone/honorduoone">源码与更新日志</a>
  &nbsp;·&nbsp;
  <a href="https://github.com/honorduoone/honorduoone/issues">问题反馈</a>
</p>

把荣耀 MagicOS 状态栏右侧的 **Wi-Fi、移动信号、电池** 合并成一个仿 iPhone「Duo」风格的三合一字形，并把圆环、胶囊与双排信号三套排版合到同一个模块里。

## 核心特性

- **三种排版，一个模块**：圆环、胶囊、双排信号三套样式，圆环/胶囊与双排信号互斥并自动提示。
- **三槽分区**：胶囊的上、中、下三个槽位可自由放置组件，中部最多 3 件并按三等分居中排布。
- **流量箭头组件**：单个组件内含两组上下行三角，左半移动数据、右半 Wi-Fi；未连接的一侧画灰占位。
- **可放置组件**：电量数字、Wi-Fi 弧、移动信号（卡一/卡二可拆）、网络制式、充电闪电、功率、温度、帧率、时钟等均可独立放置或交还系统。
- **双卡停用显示**：在系统设置里停用一张卡后，对应那一排改用未点亮点的轨道色，位置与行高不变，不显示网络制式，也不会被另一张卡的信号带亮。
- **通知中心天气**：在通知中心日期行末尾显示实时天气与气温，支持文字/图标/图标加文字三种样式，点击日期行可直接打开系统天气应用。
- **双排信号**：主卡信号柱 + 副卡圆点，支持 4/5 格切换与制式标、流量箭头附加显示。
- **鸿蒙堆叠信号**：内置 StackedSignal_5G 的图标与判定逻辑，开启后信号图标改由这套堆叠资源绘制（需重启系统界面）。
- **下拉形变 / 面板原生图标**：二者互斥，只能选其一；前者让字形随下拉形变，后者在展开面板时交还系统原生图标。
- **智能防烧屏**：OLED 屏幕的 30 秒 3×3 离散网格微移位，边界安全钳制，开销极低。
- **息屏正确交接**：全屏 AOD 复用状态栏行时把电池完整交还宿主，息屏不再缺电量图标。

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

本模块是下列三个开源项目的复刻与整合：

- **[odomu/HonorDuo](https://github.com/odomu/HonorDuo)** — 基础底座，三合一渲染引擎、分区模型与状态采样源自这里。
- **[coderstory/HonorHook](https://github.com/coderstory/HonorHook)** — 液态玻璃界面样式与部分状态栏 Hook 思路的参考实现。
- **[nisu123f/HonorDuoBar](https://github.com/nisu123f/HonorDuoBar)** — 圆环形态特性的来源，包括下拉形变、Wi-Fi 弧档位、蓝牙电量等。

另外感谢 [yixing233/HyperDuo](https://github.com/yixing233/HyperDuo)（HonorDuo 的上游）、[Miuix](https://github.com/Design-Compute/Miuix)（界面组件）、[LSPosed](https://github.com/LSPosed/LSPosed) 与 [libxposed](https://github.com/libxposed)（框架生态）。

## 许可

本项目沿用上游的 **GPL-3.0**，二次修改与再分发请同样开源。
