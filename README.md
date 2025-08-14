# 微信API代理服务

这是一个用于解决微信API CORS跨域问题的后端代理服务，可以部署到Vercel上。

## 功能特性

- 代理微信Access Token获取接口
- 代理微信JSAPI Ticket获取接口
- 自动处理CORS跨域问题
- 支持Vercel部署

## 部署到Vercel

### 1. 安装Vercel CLI
```bash
npm i -g vercel
```

### 2. 登录Vercel
```bash
vercel login
```

### 3. 部署项目
```bash
vercel
```

### 4. 生产环境部署
```bash
vercel --prod
```

## 项目结构

```
├── api/
│   ├── wechat-token.js      # 微信Access Token代理
│   └── wechat-ticket.js     # 微信JSAPI Ticket代理
├── index.html               # 前端页面
├── vercel.json              # Vercel配置
└── README.md                # 说明文档
```

## API接口

### 获取Access Token
```
GET /api/wechat-token?appid=YOUR_APPID&secret=YOUR_SECRET
```

### 获取JSAPI Ticket
```
GET /api/wechat-ticket?access_token=ACCESS_TOKEN&type=jsapi
```

## 环境变量

如果需要，可以在Vercel中设置以下环境变量：
- `WECHAT_APPID`: 微信AppID
- `WECHAT_SECRET`: 微信AppSecret

## 注意事项

1. 确保微信AppID和AppSecret正确
2. 在微信环境中测试分享功能
3. 后端代理服务有30秒超时限制
4. 建议在生产环境中添加适当的缓存机制

## 故障排除

如果遇到问题：
1. 检查Vercel函数日志
2. 确认API路由配置正确
3. 验证微信API参数
4. 检查网络连接
