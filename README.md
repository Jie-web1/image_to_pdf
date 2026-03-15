# 文件转换器 (Image to PDF & More)

图片转 PDF、图片格式/缩放、文本编码与换行符转换。支持 **Web 前端** 与命令行。

### 用自己的域名（Domain）+ HTTPS

**不需要改任何代码。** GitHub Pages 会免费提供 HTTPS（证书自动配置）。

1. **先有一个域名**  
   在域名商购买（如 Namecheap、Cloudflare、阿里云、腾讯云等），或使用免费子域名服务。

2. **在 GitHub 里绑定域名**  
   - 打开仓库 → **Settings** → **Pages**  
   - 在 **Custom domain** 里填你的域名（例如 `converter.example.com` 或 `example.com`）  
   - 勾选 **Enforce HTTPS**（强制 HTTPS）  
   - 点 **Save**

3. **在域名商那里配置 DNS**  
   - 若用**子域名**（如 `converter.example.com`）：  
     添加一条 **CNAME** 记录：  
     - 名称：`converter`（或你用的子域名前缀）  
     - 目标：`jie-web1.github.io`  
   - 若用**根域名**（如 `example.com`）：  
     添加 **A** 记录，指向 GitHub 的 IP（在 [GitHub 文档](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) 里查最新 IP），或改用 CNAME 到 `username.github.io`（部分域名商支持）。

4. **等待生效**  
   DNS 生效通常 5 分钟～48 小时。生效后访问 `https://你的域名` 即可，**HTTPS 由 GitHub 自动提供，无需改代码。**

## 功能

- **img2pdf**：多张图片合并为一个 PDF（支持 PNG、JPG、GIF、BMP、TIFF、WebP）
- **图片转换**：格式转换（PNG/JPEG/WebP/BMP/TIFF）、按比例或最大宽高缩放
- **文本编码**：UTF-8、GBK 等编码互转
- **换行符**：LF ↔ CRLF 转换

## 环境与安装

- Python 3.8+
- `pip install -r requirements.txt`

## 运行方式

**Web 前端：**

```bash
python app.py
```

浏览器打开 http://127.0.0.1:5000 ，使用页面完成转换，结果直接下载。文件仅在本地临时处理。

**命令行：**

```bash
# 图片 → PDF
python run.py img2pdf 图1.png 图2.jpg -o out.pdf

# 图片格式/缩放
python run.py image photo.png -o photo.jpg --max-size 800x600

# 文本编码
python run.py encoding file.txt -o out.txt --from-encoding gbk --to-encoding utf-8

# 换行符
python run.py line-endings file.txt -o out.txt
python run.py line-endings file.txt -o out.txt --to-crlf
```

## 项目结构

```
├── README.md
├── requirements.txt
├── app.py              # Web 服务
├── run.py              # CLI
├── templates/
├── static/
└── src/
    ├── cli.py
    └── converters/
```

## License

MIT
# image_to_PDF
