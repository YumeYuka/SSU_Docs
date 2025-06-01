# 📝 项目脚本使用指南

本文档介绍了 SSU_Docs 项目中所有可用的 npm/pnpm 脚本命令。

## 🚀 开发相关

### 基础开发命令

```bash
# 启动开发服务器 (端口: 25527)
pnpm dev

# 启动开发服务器并允许外部访问
pnpm dev:host

# 启动开发服务器 (调试模式)
pnpm dev:debug
```

### 构建相关

```bash
# 构建生产版本
pnpm build

# 清理后构建 (推荐用于解决缓存问题)
pnpm build:clean

# 测试构建结果
pnpm test:build

# 分析构建产物大小
pnpm analyze
```

### 预览相关

```bash
# 预览构建结果
pnpm preview

# 预览构建结果 (指定端口 4173)
pnpm preview:dist

# 等同于 preview
pnpm serve
```

## 🧹 清理相关

### 缓存清理

```bash
# 清理所有缓存、临时文件和构建产物
pnpm clean

# 只清理缓存文件
pnpm clean:cache

# 只清理构建产物
pnpm clean:dist

# 只清理临时文件
pnpm clean:temp

# 清理 node_modules 和 lock 文件
pnpm clean:node_modules

# 完全清理 (包括 node_modules)
pnpm clean:all
```

### 清理说明

- `clean:cache`: 清理 VitePress 缓存和 Node.js 模块缓存
- `clean:dist`: 清理构建输出目录
- `clean:temp`: 清理所有临时文件
- `clean:node_modules`: 删除依赖包和锁定文件
- `clean:all`: 执行完整清理

## 📦 依赖管理

### 依赖检查和更新

```bash
# 检查过期的依赖包
pnpm deps:check

# 更新所有依赖包到最新版本
pnpm deps:update

# 安装依赖包
pnpm deps:install

# 重新安装所有依赖包 (完全重装)
pnpm deps:reinstall
```

## 🛠️ 故障排除

### 常见问题解决方案

#### 1. 构建失败或缓存问题

```bash
# 推荐的解决步骤
pnpm clean        # 清理缓存
pnpm build        # 重新构建
```

#### 2. 依赖包问题

```bash
# 完全重装依赖
pnpm deps:reinstall
```

#### 3. 开发服务器问题

```bash
# 清理后重启开发服务器
pnpm clean:cache
pnpm dev
```

#### 4. 端口冲突

```bash
# 使用不同端口启动
pnpm dev:host
```

## 🔍 调试和分析

### 调试模式

```bash
# 启用 VitePress 调试输出
pnpm dev:debug
```

### 构建分析

```bash
# 分析构建产物大小和依赖关系
pnpm analyze
```

## 📋 推荐工作流程

### 日常开发

```bash
# 1. 启动开发
pnpm dev

# 2. 开发完成后测试构建
pnpm test:build
```

### 部署前检查

```bash
# 1. 清理并构建
pnpm build:clean

# 2. 预览构建结果
pnpm preview
```

### 遇到问题时

```bash
# 1. 完全清理
pnpm clean:all

# 2. 重新安装依赖
pnpm deps:install

# 3. 重新构建
pnpm build
```

## 💡 提示

1. **优先使用 `pnpm`**: 项目配置为使用 pnpm 包管理器
2. **定期清理**: 建议定期运行 `pnpm clean` 清理缓存
3. **依赖更新**: 定期检查和更新依赖包 `pnpm deps:check`
4. **构建前清理**: 重要构建前建议使用 `pnpm build:clean`
5. **调试问题**: 遇到奇怪问题时优先尝试 `pnpm clean`

## 🆘 获取帮助

如果遇到问题，请按以下顺序尝试：

1. 运行 `pnpm clean` 清理缓存
2. 运行 `pnpm deps:reinstall` 重装依赖
3. 检查 Node.js 版本是否兼容
4. 查看控制台错误信息
5. 联系项目维护者

---

*最后更新: 2025年6月2日*
