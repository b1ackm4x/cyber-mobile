# 赛博手机 · cyber-mobile

**An interactive, browser-based 3D replica of the BlackBerry Classic (Q20) running a recreated BB10 interface. Unofficial fan project.**

在浏览器里把玩一台 BlackBerry Classic（Q20）：可旋转的 3D 机身、能按下去的物理键盘，屏幕里跑着还原的 BB10 系统。

![赛博手机首屏](screenshots/01-hero.jpg)

![操作演示：切换视角、打字搜索并打开应用](screenshots/demo.gif)

> 本仓库只包含网页的构建产物（静态文件），不含源码。

## 特性

- **3D 机身**：自行建模、对照实机照片还原，可拖动旋转、滚轮 / 双指缩放；预设视角：整机、键盘、侧看键程、背面、摄像头、侧键、顶部。
- **材质区分**：屏幕玻璃与前面板分开处理，各自有不同的反光；背面是织纹质感。
- **可按下的键盘**：键帽和侧键都能点按（有键程和按键声），也可以直接用电脑键盘打字。
- **背光与关灯**：一键打开键盘背光，或关灯看暗处的样子。
- **BB10 系统界面**：屏幕是实时渲染的 BB10 桌面——多页应用、Active Frames、BlackBerry Hub、下拉快捷设置、全局搜索、锁屏、音量提示。
- **触控板与触摸**：屏幕可触摸滑动，屏幕下方触控板可滑动移动焦点、按下确认。
- **可用的应用**：Hub、时钟、计算器、设置、Term49 终端（模拟 zsh，支持 `ls`、`cd`、`cat`、`git`、`neofetch` 等常用命令）。桌面上其它图标只是外观，暂未实现。
- **新手引导**：首次访问自动弹出，逐步带你试滑动、触控板、键盘搜索和视角切换，右上角「新手引导」可随时重看。
- **手机也能用**：页面按手机竖屏做了布局，支持触控操作。

## 截图

### 机身

| 键盘 | 侧看键程 |
|---|---|
| ![键盘](screenshots/02-keyboard.jpg) | ![侧看键程](screenshots/03-key-travel.jpg) |

| 背面 | 摄像头 |
|---|---|
| ![背面](screenshots/04-back.jpg) | ![摄像头](screenshots/05-camera.jpg) |

| 侧键 | 顶部 |
|---|---|
| ![侧键](screenshots/06-side-buttons.jpg) | ![顶部](screenshots/07-top.jpg) |

| 关灯与键盘背光 | 自由旋转 |
|---|---|
| ![关灯](screenshots/08-dark-backlight.jpg) | ![斜视](screenshots/09-oblique.jpg) |

### BB10 系统与应用

| 桌面 | Hub | 快捷设置 | 全局搜索 |
|---|---|---|---|
| ![桌面](screenshots/12-bb10-home.jpg) | ![Hub](screenshots/13-bb10-hub.jpg) | ![快捷设置](screenshots/14-quick-settings.jpg) | ![搜索](screenshots/15-global-search.jpg) |

| 计算器 | 时钟 | 设置 | Term49 终端 |
|---|---|---|---|
| ![计算器](screenshots/16-calculator.jpg) | ![时钟](screenshots/17-clock.jpg) | ![设置](screenshots/18-settings.jpg) | ![终端](screenshots/19-terminal.jpg) |

### 引导与手机布局

| 新手引导 | 手机竖屏 |
|---|---|
| ![引导](screenshots/10-tour.jpg) | <img src="screenshots/11-mobile.jpg" width="260" alt="手机竖屏"> |

## 怎么玩

**3D 视角**
- 鼠标：拖动旋转，滚轮缩放；触屏：单指旋转，双指缩放。
- 底部工具栏切换预设视角，「背光」「关灯」「声音」为开关。

**操作手机**
- 点屏幕图标打开应用；从屏幕底边向上滑回桌面；左右滑动翻页，向右滑到头是 Hub；从顶部下拉打开快捷设置。
- 触控板（屏幕与键盘之间的小方块）：滑动移动焦点，按下确认；也可以用电脑方向键。
- 键盘：点按键帽，或直接敲电脑键盘。在桌面上打字会打开全局搜索（如输入 `clock`）。
- 侧键：点按音量键会出现音量提示。

## 技术栈

以下均来自项目依赖：

- React 19 + TypeScript + Vite
- three.js、@react-three/fiber、@react-three/drei、@react-three/postprocessing（3D 渲染与后期）
- PixiJS 8（BB10 屏幕画面渲染成贴图贴到模型屏幕上）
- glTF 模型（`models/q20.glb`），按键动画为程序驱动

## 本地运行

这是纯静态产物，资源路径为相对路径，任意静态服务器都能跑，也可放在子路径下：

```bash
git clone https://github.com/b1ackm4x/cyber-mobile.git
cd cyber-mobile
npx serve .
```

然后打开终端里提示的地址。不要直接双击 `index.html`（浏览器会拦截 file:// 下的模型加载）。需要支持 WebGL 的现代浏览器。

## 声明

- 这是非官方的粉丝作品，仅作学习和怀旧展示，不用于商业用途。
- BlackBerry、BB10 及相关标识、界面素材的商标和版权归 BlackBerry Limited 所有，与本项目作者无关。
- 3D 模型与贴图为本项目自行建模，对照实机照片还原；BB10 界面素材来自实机截图。若有侵权，请联系作者删除。

## 作者

[b1ackm4x](https://github.com/b1ackm4x)
