# Hexo Blog

一个基于 Hexo 的静态博客项目，使用 Landscape 主题。

## 🚀 快速开始

### 安装依赖
```bash
yarn install
```

### 开发服务器
```bash
yarn dev
# 或者
yarn start
# 或者
yarn server
```

访问 http://localhost:4000 预览博客。

## 📝 内容管理

### Obsidian 笔记集成
本博客使用 `obsidian-notes` 仓库作为 `source` 目录的内容源。

**工作流程：**
1. 在 Obsidian 中编辑笔记（`source` 目录）
2. 提交到 `obsidian-notes` 仓库：
   ```bash
   cd source
   git add .
   git commit -m "Update notes"
   git push origin main
   ```
3. ✅ **自动完成**：GitHub Actions 会自动：
   - 更新博客仓库的子模块引用
   - 触发博客部署
   - 更新网站内容

**无需手动操作 blog 仓库！**

### 创建内容
```bash
# 创建新文章
yarn new:post "文章标题"

# 创建新页面
yarn new:page "页面标题"

# 创建草稿
yarn new:draft "草稿标题"
```

### 构建和部署
```bash
# 构建静态文件
yarn build

# 清理缓存
yarn clean

# 一键发布（清理 + 生成 + 部署）
yarn publish

# 仅部署
yarn deploy
```

## 🛠️ 项目结构

```
blog/
├── _config.yml          # Hexo 配置文件
├── _config.landscape.yml # Landscape 主题配置
├── source/              # 源文件目录
│   └── _posts/          # 文章目录
├── scaffolds/           # 模板文件
├── themes/              # 主题目录
└── public/              # 生成的静态文件（自动生成）
```

## 📋 常用工作流程

### 1. 开发新文章
```bash
# 创建文章
yarn new:post "我的新文章"

# 启动开发服务器预览
yarn dev

# 编辑 source/_posts/ 目录下的文章文件
```

### 2. 发布文章
```bash
# 一键发布到线上
yarn publish
```

### 3. 本地构建测试
```bash
# 清理并重新构建
yarn clean
yarn build

# 查看 public/ 目录中的生成文件
```

## 🔧 配置说明

- **站点配置**：编辑 `_config.yml`
- **主题配置**：编辑 `_config.landscape.yml`
- **部署配置**：在 `_config.yml` 的 `deploy` 部分配置

## 📚 相关链接

- [Hexo 官方文档](https://hexo.io/zh-cn/docs/)
- [Landscape 主题](https://github.com/hexojs/hexo-theme-landscape)

## 📄 许可证

MIT License
