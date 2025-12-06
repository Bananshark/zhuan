# AR文物智能介绍系统

## 项目结构

```
新建文件夹 (4)/
├── index.html          # 主程序文件
├── config.json         # 配置文件
├── README.md          # 说明文档
├── mind/              # AR识别目标文件
│   └── two_wenwu.mind # MindAR识别文件
├── model/             # 3D模型文件
│   ├── ding.glb       # 青铜鼎模型
│   ├── 铜龙桌子三维模型.glb  # 铜龙桌子模型
│   ├── Fe_foot.gltf   # 其他模型文件
│   └── table.gltf     # 其他模型文件
└── img/               # 识别图片（参考）
    ├── Fefoot.jpg
    └── table.jpg
```

## 功能说明

1. **AR识别功能**
   - 使用MindAR识别图像目标
   - 识别成功后显示3D模型

2. **文物介绍面板**
   - AR识别到目标时，右侧自动弹出介绍面板
   - 显示文物标题和详细介绍

3. **AI聊天功能**
   - 识别到目标且配置API后，右下角显示聊天窗口
   - 可与AI对话了解更多文物信息

## 使用方法

1. **启动本地服务器**
   ```bash
   # 方法1：使用Python
   python -m http.server 5500
   
   # 方法2：使用Node.js
   npx serve . -p 5500
   ```

2. **访问页面**
   打开浏览器访问：`http://localhost:5500/index.html`

3. **配置API**
   - 点击右上角⚙按钮
   - 填写API地址、API密钥和应用ID
   - 点击保存配置

4. **使用AR功能**
   - 将摄像头对准识别图片（Fefoot.jpg 或 table.jpg）
   - 识别成功后会自动显示3D模型和介绍面板
   - 可在聊天窗口与AI对话

## 配置说明

### config.json

- `api`: API配置信息
- `textDisplay`: 文字显示速度配置
- `ui`: 界面文本配置
- `artifacts`: 文物信息配置（可在代码中修改）

### 文物信息配置

文物信息在 `index.html` 的 `artifactInfo` 对象中配置：

```javascript
const artifactInfo={
  0:{title:"青铜鼎",content:"..."},
  1:{title:"铜龙桌子",content:"..."}
};
```

## 注意事项

1. 必须通过HTTP服务器运行，不能直接用file://协议打开
2. 需要摄像头权限才能使用AR功能
3. AI聊天功能需要配置有效的API信息
4. 识别图片需要与two_wenwu.mind文件匹配

