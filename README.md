# 🖐️ Hand Gesture Product Animation

手势控制产品拆装动画 — 摄像头识别手势，手张开零件散开，握拳零件归位。

## Demo

- ✋ 手掌张开 → 产品拆解成零件
- ✊ 握拳收拢 → 零件组装回产品
- 手势开合程度实时控制动画进度

## Quick Start

1. 启动本地服务器（需要 HTTPS 或 localhost 才能使用摄像头）：

```bash
# Python
python -m http.server 8080

# Node.js
npx serve -l 8080

# 双击启动服务.bat (Windows)
```

2. 打开浏览器访问 `http://localhost:8080`
3. 允许摄像头权限
4. 伸出手掌控制动画！

## Tech Stack

- **MediaPipe Hands** — 实时手部关键点检测
- **Canvas API** — 动画渲染
- **Vanilla JS** — 零依赖，纯前端实现

## Files

| File | Description |
|------|-------------|
| `index.html` | 主应用（手势识别 + 动画控制） |
| `animation.mp4` | 拆解动画视频 |
| `product-assembled.png` | 产品完整图 |
| `product-parts.png` | 产品拆分图 |

## How It Works

1. MediaPipe 识别手掌 21 个关键点
2. 计算 5 根手指的伸展程度（指尖到手腕距离 vs 关节到手腕距离）
3. 开合度 0-1 映射到动画进度
4. 平滑插值避免抖动

## Browser Support

- Chrome 90+ ✅
- Edge 90+ ✅
- Firefox ✅ (需手动启用手势API)
- Safari ⚠️ (部分支持)

## License

MIT
