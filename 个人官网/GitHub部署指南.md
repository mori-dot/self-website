# GitHub部署指南

## 问题说明

当您将网站部署到GitHub仓库后，通过GitHub Pages访问时，可能会发现上传的图片无法显示。这是因为：

- 本地上传的图片存储在浏览器的localStorage中，只在本地有效
- GitHub Pages访问时使用的是不同的浏览器环境，无法访问本地存储的图片

## 解决方案

要在GitHub上部署并让外部访问看到图片，需要将图片作为静态文件上传到GitHub仓库中。

### 步骤1：准备图片文件

1. **创建images文件夹**：在项目根目录创建一个名为`images`的文件夹
2. **保存图片**：将您想要显示的图片保存到这个文件夹中
   - 个人照片：建议命名为`personal.jpg`
   - Listing截图：建议命名为`listing1.jpg`、`listing2.jpg`等

### 步骤2：修改HTML文件

#### 修改首页（index.html）

1. 找到个人照片的HTML部分
2. 将图片路径修改为相对路径，例如：

```html
<!-- 修改前 -->
<img src="${savedPhoto}" style="max-width: 200px; max-height: 200px; border-radius: 50%; margin-bottom: 20px;">

<!-- 修改后 -->
<img src="images/personal.jpg" style="max-width: 200px; max-height: 200px; border-radius: 50%; margin-bottom: 20px;">
```

#### 修改案例展示页（portfolio.html）

1. 找到每个Listing截图的HTML部分
2. 将图片路径修改为相对路径，例如：

```html
<!-- 修改前 -->
<img src="${imageData}" class="portfolio-image">

<!-- 修改后 -->
<img src="images/listing1.jpg" class="portfolio-image">
```

### 步骤3：部署到GitHub

1. **初始化git仓库**（如果尚未初始化）：
   ```bash
   git init
   ```

2. **添加所有文件**：
   ```bash
   git add .
   ```

3. **提交更改**：
   ```bash
   git commit -m "添加网站文件和图片"
   ```

4. **推送到GitHub**：
   ```bash
   git remote add origin https://github.com/yourusername/your-repo.git
   git push -u origin main
   ```

5. **启用GitHub Pages**：
   - 进入GitHub仓库设置
   - 找到"Pages"选项
   - 选择"main"分支作为源
   - 点击"Save"

### 步骤4：验证部署

1. 等待几分钟让GitHub Pages构建完成
2. 访问GitHub Pages提供的URL
3. 确认图片是否正常显示

## 注意事项

1. **图片大小**：建议图片大小不超过2MB，以确保加载速度
2. **图片格式**：推荐使用JPG、PNG格式
3. **路径格式**：确保使用相对路径（如`images/personal.jpg`）而不是绝对路径
4. **文件命名**：避免使用中文和特殊字符作为文件名

## 故障排除

如果图片仍然无法显示：

1. 检查图片文件是否正确上传到GitHub仓库
2. 确认图片路径是否正确
3. 清除浏览器缓存后重新访问
4. 检查GitHub Pages构建状态是否成功

通过以上步骤，您的网站部署到GitHub后，外部访问时就能正常看到所有图片了。