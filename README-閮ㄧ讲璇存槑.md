# 大耳帽兜冰淇淋甜筒 · GitHub Pages 部署

纯静态页面，无需构建，所有资源都是相对路径，放在仓库任意位置都能跑。

## 方法一：仓库根目录（推荐，最快）
1. 新建一个 GitHub 仓库（比如 `cinna-ice-cream-cone`）。
2. 把本文件夹里的所有文件（含 `.nojekyll`）传到仓库根目录。
3. 仓库 Settings → Pages → Source 选 `main` 分支 / `(root)`，保存。
4. 等一两分钟，访问 `https://<你的用户名>.github.io/<仓库名>/`。

## 方法二：子目录
把 `site/` 整个文件夹放进现有仓库（如 `docs/` 或 `games/cone/`），
Pages 里 Source 选对应目录即可，路径不用改（全部是相对路径）。

## 本地预览
```
cd site
python3 -m http.server 8080
# 打开 http://localhost:8080
```
（直接双击 index.html 用 file:// 打开也能玩，但个别浏览器会限制模型加载，建议起个本地服务。）

## 文件说明
- index.html / style.css / game.bundle.js — 页面与逻辑（已打包，无外部依赖）
- assets/model/…glb — Blender 建模的 3D 甜筒（meshopt 压缩，1.1 MB）
- assets/ui/…webp — 按钮与设计说明配图
- assets/audio/ — 背景音乐与完成音效
- .nojekyll — 跳过 GitHub Pages 的 Jekyll 处理
