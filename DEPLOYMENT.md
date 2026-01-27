# 快速部署指南

## 方法1: 直接使用GitHub Pages（推荐）

### 步骤：

1. **创建GitHub仓库**
   ```bash
   # 在GitHub网站上创建新仓库，例如: dormitory-system
   # 可以选择Public或Private
   ```

2. **上传文件**
   ```bash
   git clone https://github.com/your-username/dormitory-system.git
   cd dormitory-system
   
   # 将以下文件复制到仓库目录：
   # - index-enhanced.html (重命名为 index.html)
   # - README.md
   # - .github/workflows/deploy.yml (可选，用于自动部署)
   
   cp index-enhanced.html index.html
   git add .
   git commit -m "初始化宿舍管理系统"
   git push origin main
   ```

3. **启用GitHub Pages**
   - 进入仓库 Settings
   - 左侧菜单选择 "Pages"
   - Source 选择 "GitHub Actions"
   - 保存

4. **访问系统**
   - 等待部署完成（约1-2分钟）
   - 访问：`https://your-username.github.io/dormitory-system/`

## 方法2: 本地直接使用

如果不需要在线访问，可以：

1. 下载 `index-enhanced.html`
2. 重命名为 `index.html`
3. 用浏览器打开
4. 配置GitHub Token后即可使用

**优点**: 
- 无需部署
- 数据仍然同步到GitHub
- 可在任何设备的浏览器中打开

## 获取GitHub Token

### 详细步骤：

1. 登录GitHub
2. 点击右上角头像 → **Settings**
3. 左侧菜单滚动到底部 → **Developer settings**
4. 选择 **Personal access tokens** → **Tokens (classic)**
5. 点击 **Generate new token (classic)**
6. 填写表单：
   - **Note**: `Dormitory System Data Sync`
   - **Expiration**: `No expiration` (或选择90天/1年)
   - **Select scopes**: 只勾选 **gist**
7. 点击 **Generate token**
8. **立即复制Token**（只显示一次！）

### Token格式示例：
```
ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## 配置步骤

1. **打开系统**（本地或在线）

2. **首次设置密码**
   - 系统会自动提示"首次使用提醒"
   - 点击"立即设置"按钮
   - 为管理员和查看者设置安全密码（至少6位）
   - 完成设置

3. **使用新密码登录**
   - 用户名: `admin` 或 `viewer`
   - 密码: 您刚才设置的密码

4. **配置GitHub同步**
   - 点击顶部"系统设置"标签
   - 粘贴您的GitHub Token
   - 点击"保存配置"
   - 点击"测试连接"（应该显示成功）
   - 点击右上角"同步数据"按钮

## 数据迁移

### 从旧系统迁移：

如果您已经在使用旧版本的系统：

1. 在旧系统中导出Excel文件
2. 在新系统中使用"批量导入"功能
3. 导入完成后点击"同步数据"

### 在多台设备使用：

**设备A**（首次配置）:
1. 配置GitHub Token
2. Gist ID留空（系统会自动创建）
3. 添加数据并同步

**设备B**（同步已有数据）:
1. 配置**相同的**GitHub Token
2. 在设备A查看并复制Gist ID：
   - 进入"系统设置"
   - 复制"Gist ID"框中的内容
3. 在设备B粘贴Gist ID
4. 保存配置
5. 刷新页面，数据会自动从云端加载

## 安全建议

1. **首次使用强制设置密码**
   - 系统会自动提示初始化设置
   - 必须完成密码设置才能使用系统
   - 设置后默认密码永久失效

2. **定期修改密码**
   - 登录后进入"系统设置"
   - 管理员可随时修改任何用户密码
   - 建议每3-6个月更换一次

3. **保护GitHub Token**
   - 不要将Token分享给他人
   - 不要在公开场合展示Token
   - 定期更换Token

4. **备份策略**
   - 定期同步数据到GitHub
   - 定期导出Excel作为本地备份
   - GitHub Gist有版本历史可恢复

## 故障排除

### 问题1: 页面无法访问
- 检查GitHub Pages是否已启用
- 等待1-2分钟让部署完成
- 清除浏览器缓存

### 问题2: 同步失败
- 检查Token是否正确
- 检查Token是否有gist权限
- 检查网络连接

### 问题3: 数据不一致
- 点击"同步数据"强制同步
- 如果多设备同时编辑，以最后同步的为准

## 联系方式

如有技术问题，可以：
1. 查看GitHub仓库的Issues
2. 查看浏览器控制台(F12)的错误信息
3. 检查README.md中的详细文档

---

**祝使用愉快！** 🎉
