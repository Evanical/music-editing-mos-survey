# 音乐编辑 MOS 主观评价问卷 — GitHub Pages 版

这个文件夹可以直接作为 GitHub Pages 静态网站使用。

## 文件结构

```text
music-editing-mos/
├── index.html
├── .nojekyll
└── audio/
    ├── mos01_source.mp3
    ├── mos01_edited.mp3
    ├── ...
    ├── pref01_source.mp3
    ├── pref01_A.mp3
    └── pref01_B.mp3
```

## 你主要需要编辑哪里？

使用 VS Code、Notepad++ 或其他代码编辑器打开 `index.html`。

搜索：

```javascript
const MOS_ITEMS = [
```

这里填写 35 道 MOS 题的：
- `sourceAudio`
- `sourceDescription`
- `instruction`
- `editedAudio`

再搜索：

```javascript
const PREFERENCE_ITEMS = [
```

这里填写 10 道偏好测试的：
- `sourceAudio`
- `sourceDescription`
- `instruction`
- `resultA`
- `resultB`

如果音频放在仓库中的 `audio/` 文件夹，请始终使用类似：

```text
audio/mos01_source.mp3
```

不要写 Windows 本地路径，例如 `C:\Users\...`。

## GitHub Pages 部署

1. 登录 GitHub。
2. 新建一个 repository，例如 `music-editing-mos-survey`。
3. 将本文件夹中的 `index.html`、`.nojekyll` 和 `audio/` 文件夹上传到仓库根目录。
4. 打开仓库 `Settings` → `Pages`。
5. 在 `Build and deployment` 中将 `Source` 选择为 `Deploy from a branch`。
6. Branch 选择 `main`，Folder 选择 `/(root)`，点击 `Save`。
7. 等待 GitHub 完成部署后，Pages 设置页会显示公开网址。

项目仓库方式的网址通常类似：

```text
https://你的GitHub用户名.github.io/music-editing-mos-survey/
```

## 注意

当前版本的“导出 CSV”会把评分下载到参与者自己的电脑，不会自动上传给研究者。
如果你需要参与者点击“提交”后，数据自动进入 Google Sheets / Supabase / Firebase，
还需要额外接入一个在线数据后端。
