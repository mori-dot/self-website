# GitHub部署自查指南

## 问题分析

当部署到GitHub后图片无法显示，可能的原因包括：

1. 图片文件未上传到GitHub仓库
2. 图片路径设置错误
3. GitHub Pages未正确启用
4. 仓库名称或URL配置错误
5. 浏览器缓存问题

## 自查步骤

### 步骤1：检查GitHub仓库文件结构

1. **登录GitHub**：进入 `https://github.com/mori-dot/self-website2`
2. **检查文件结构**：
   - 确认根目录下是否存在 `images` 文件夹
   - 确认 `images` 文件夹中是否包含以下文件：
     - `personal.jpg.jpg`
     - `listing1.jpg`
     - `listing2.jpg`
     - `listing3.jpg`
     - `listing4.jpg`

### 步骤2：检查GitHub Pages设置

1. **进入仓库设置**：点击仓库页面右上角的 "Settings"
2. **找到Pages选项**：在左侧菜单中点击 "Pages"
3. **检查构建来源**：
   - 确保 "Source" 设置为 "Deploy from a branch"
   - 确保 "Branch" 设置为 "main" 或 "master"
   - 确保 "Folder" 设置为 "/ (root)"
4. **检查部署状态**：
   - 查看页面底部的 "GitHub Pages" 状态
   - 确保显示 "Your site is live at https://mori-dot.github.io/self-website2/"

### 步骤3：检查图片路径

1. **检查个人照片路径**：
   - 路径应为：`https://mori-dot.github.io/self-website2/images/personal.jpg.jpg`
   - 在浏览器中直接访问此URL，检查是否能显示图片

2. **检查Listing截图路径**：
   - 路径应为：`https://mori-dot.github.io/self-website2/images/listing1.jpg`
   - 在浏览器中直接访问此URL，检查是否能显示图片

### 步骤4：检查文件名和格式

1. **检查文件名**：
   - 个人照片文件名应为 `personal.jpg.jpg`（或改为 `personal.jpg` 并更新路径）
   - Listing截图文件名应为 `listing1.jpg` 等

2. **检查文件格式**：
   - 确保图片文件格式为JPG或PNG
   - 确保文件大小不超过GitHub的限制（建议不超过2MB）

### 步骤5：清除浏览器缓存

1. **清除缓存**：
   - Chrome：Ctrl+Shift+Delete → 选择 "缓存的图片和文件" → 点击 "清除数据"
   - Firefox：Ctrl+Shift+Delete → 选择 "缓存" → 点击 "清除"
   - Safari：Cmd+Option+E → 点击 "清除"

2. **硬刷新页面**：
   - Windows/Linux：Ctrl+F5
   - Mac：Cmd+Shift+R

### 步骤6：检查网络连接

1. **确认网络连接**：确保您的网络连接正常
2. **检查GitHub状态**：访问 `https://www.githubstatus.com/` 确认GitHub服务正常

## 常见问题解决方案

### 问题1：图片文件未上传到GitHub

**解决方案**：
```bash
# 确保所有文件都已添加到Git
 git add .

# 提交更改
git commit -m "添加所有文件"

# 推送到GitHub
git push origin main
```

### 问题2：图片路径错误

**解决方案**：
- 检查HTML文件中的图片路径是否正确
- 确保路径与GitHub仓库中的实际文件路径一致
- 尝试使用相对路径：`images/personal.jpg`

### 问题3：GitHub Pages未构建

**解决方案**：
- 等待几分钟让GitHub Pages构建完成
- 检查仓库设置中的Pages选项，确保配置正确
- 尝试重新部署：在Pages设置页面点击 "Save" 按钮

### 问题4：文件名错误

**解决方案**：
- 将 `personal.jpg.jpg` 重命名为 `personal.jpg`
- 更新HTML文件中的图片路径
- 重新提交并推送更改

## 验证部署

1. **访问网站**：`https://mori-dot.github.io/self-website2/`
2. **检查图片**：确认个人照片和Listing截图是否正常显示
3. **测试功能**：点击图片查看放大效果

## 联系支持

如果以上步骤都无法解决问题，可以：

1. 检查GitHub Pages的构建日志
2. 在GitHub仓库的 "Issues" 页面创建问题
3. 联系GitHub支持团队

通过以上自查步骤，您应该能够找到并解决图片显示问题。