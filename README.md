# 文件转换器 (Image to PDF & More)

图片转 PDF、图片格式/缩放、文本编码与换行符转换。支持 **Web 前端** 与命令行。

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
