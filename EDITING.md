# 修改个人主页

网站地址（发布成功后）：https://christong9.github.io/

这是单文件静态网页；不需要安装依赖或运行构建。用代码编辑器打开 index.html，保存后用浏览器打开文件即可预览。

## 添加个人照片

1. 将照片上传到 assets/ 文件夹，例如 assets/portrait.jpg。
2. 在 index.html 中搜索 `"portrait": ""`。
3. 将该项改为 `"portrait": "assets/portrait.jpg"`，保留末尾逗号。
4. 当前照片框为正方形，默认居中裁切；文件名和大小写需与路径一致。

## 修改简介

在 index.html 中搜索 `<div class="bio">`，修改对应的段落文字。当前简介聚焦多模态学习与生成、AI agents、导师与实验室合作，以及艺术和个人兴趣。

## 修改链接、论文和作品

在 index.html 中搜索 `id="site-content"`，修改下方 JSON：

- `links`：GitHub、Google Scholar、LinkedIn、两个邮箱和 CV。
- `publications`：论文标题、作者顺序、venue、年份、摘要、结果和链接。
- `artworks`：艺术作品。
- `installations`：装置作品。
- `portrait`：个人照片路径。
- `authorName`：论文作者列表里需要加粗的姓名。

JSON 的引号、逗号和括号需要保持有效。论文等内容由此配置生成。文件里的 CONTENT GUIDE 提供了填写示例。

Harmony 目前标注为 Under review at TMLR。完整作者顺序尚待补充；拿到真实顺序后填写其 authors 字段。

## 添加艺术作品

将图片上传到 assets/，例如 assets/work-01.jpg。在 artworks 数组里加入：

```json
{
  "title": "真实作品名称",
  "year": "2026",
  "medium": "媒介与尺寸",
  "image": "assets/work-01.jpg",
  "alt": "描述作品画面的替代文字",
  "description": "作品说明",
  "video": "",
  "url": ""
}
```

装置作品使用 installations 数组。video 可填写 assets/ 下的 MP4 或 WebM 路径。添加多个条目时，用逗号分隔 JSON 对象。

## 发布更新

GitHub Pages 应设置为：Deploy from a branch → main → / (root)。
把修改提交到发布分支后，等待 GitHub Actions 中的 Pages 部署完成。

本地添加的图片、视频或 PDF 需要与 index.html 一起提交。仅修改本地文件不会更新线上网站。
