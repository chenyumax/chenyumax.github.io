# 陈宇的小宇宙

一个温和、有一点惊喜的个人主页。以奶油白、薄荷绿和杏桃色为主，展示一个正在慢慢生长的个人空间，不以作品数量或履历撑满页面。

## 技术与依赖

- Vue 3 + TypeScript，使用 Composition API 和 `<script setup>`
- Vite + `@vitejs/plugin-vue`：开发与打包
- `@lucide/vue`：按需导入的 SVG 图标
- `vue-tsc`：Vue 单文件组件类型检查
- 原生 CSS：主题变量、响应式布局、星球与窗景插画
- GitHub Actions：构建并部署到 GitHub Pages

当前是单页锚点导航，不需要 Vue Router、Pinia 或大型组件库。没有外部图片、在线字体、后端请求或追踪脚本；收藏链接需要访问相应外部网站。

## 本地使用

需要 Node.js 22.12+ 和 npm 10+，推荐 Node.js 22 LTS。

```bash
npm ci
npm run dev
```

其他命令：

```bash
npm run typecheck # Vue 与配置文件的 TypeScript 类型检查
npm run build     # 类型检查 + 生产打包，输出到 dist/
npm run preview   # 预览已生成的 dist/
```

上述开发、构建和预览命令仅供手动使用。本次初始化未启动服务、未执行构建或功能测试。

## 页面内容

- **首屏**：自我介绍、CSS 星球、漂浮标签与引导入口。
- **小小角落**：可以换一句的短文案、窗景插画、小站当前状态。
- **随手收藏**：第一组网站推荐，支持全部 / 漫游 / 灵感 / 工具分类。
- **关于这里**：关于这个小站为什么开始的一封短笺，以及 GitHub 联系入口。
- **配色切换**：右上角按钮切换薄荷绿与杏桃色，当前页面会话有效。

文案是根据建站想法拟定的第一版，不是已确认的个人履历；推荐网站也不代表真实的个人收藏。上线前可按实际喜好调整。

## 修改内容与样式

| 文件 | 用途 |
| --- | --- |
| `src/content/site.ts` | 姓名、品牌、GitHub、介绍、短句和推荐链接 |
| `src/components/HeroSection.vue` | 首屏标题、引导文案与布局 |
| `src/components/PlanetScene.vue` | CSS 星球插画 |
| `src/components/CornerSection.vue` | 生活角落与窗景插画 |
| `src/components/ThoughtCard.vue` | 短句切换 |
| `src/components/CollectionSection.vue` | 推荐分类和卡片 |
| `src/components/AboutSection.vue` | 关于区域 |
| `src/styles/tokens.css` | 主题配色、字体变量 |
| `src/styles/main.css` | 公共布局和基础样式 |
| `index.html` | 网页标题、描述、浏览器主题色 |
| `public/favicon.svg` | 本地站点图标 |

已适配桌面和移动端，提供键盘焦点样式、跳过导航入口，并尊重系统的“减少动态效果”设置。

## 部署到 GitHub Pages

已提供 `.github/workflows/deploy.yml`，推送到 `main` 后自动部署，也支持手动触发。需要先完成以下仓库设置：

1. 在 GitHub 仓库打开 **Settings → Pages**。
2. 将 **Build and deployment → Source** 设置为 **GitHub Actions**。
3. 提交并推送代码到 `main`，在 Actions 中查看部署结果。

工作流从 GitHub Pages 读取实际 `base_path`，通过 `VITE_BASE_PATH` 传给 Vite，兼容项目路径与根路径。没有在本地执行远程推送或发布。

### 关于当前网址

当前仓库为 `Chen-Yu88/chenyu.github.io`。由于仓库名不是账号对应的 `Chen-Yu88.github.io`，它按项目站点托管，未绑定自定义域名时，预期网址为：

```text
https://chen-yu88.github.io/chenyu.github.io/
```

最终以 GitHub **Settings → Pages** 显示的地址为准。

如果希望地址是 `https://chen-yu88.github.io/`，需将仓库重命名为 `Chen-Yu88.github.io`。如果希望使用其他域名，则需要单独配置自定义域名与 DNS；仅将仓库命名为 `chenyu.github.io` 并不能获得这个域名。
