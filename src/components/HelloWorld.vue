<script setup>
    import { onMounted, ref } from 'vue'

    onMounted(() => {
    
    })

    const status = ref('等待设置分享信息...')

    // const shareData = {
    //     title:    'QQ分享卡片示例',
    //     desc:     '演示QQ卡片分享功能',
    //     share_url:'https://xbuilder-test.qiniu.io/',
    //     image_url:'https://i.gtimg.cn/open/app_icon/05/58/35/77/1105583577_100_m.png'
    // };


    // // 按钮点击
    // const handleShare = () => {
    //     if (window.mqq && mqq.device && mqq.device.isMobileQQ()) {
    //         window.mqq.invoke('data', 'setShareInfo', shareData);
    //         alert('已设置，右上角··· → 分享给好友');
    //     } else {
    //         alert('请在 QQ 内置浏览器打开');
    //     }
    // };

    // 页面加载时尝试自动设置分享信息（可选）
    // onMounted(() => {
    //     // 判断是不是 QQ 内置浏览器
    //     // 注册
    //     if (window.mqq && mqq.device && mqq.device.isMobileQQ()) {
    //         window.mqq.invoke('data', 'setShareInfo', shareData);
    //     }
    // })
</script>

<template>
  <div class="container">
      <h1>QQ分享卡片功能示例</h1>
      <p>点击下方按钮设置分享信息，在QQ中通过右上角菜单分享卡片式链接</p>
      
      <div class="qr-code">
          <img src="https://api.qrserver.com/v1/create-qr-code/?size=180x180&data=https://xbuilder-test.qiniu.io/" alt="QQ分享二维码">
          <div class="qr-label">使用QQ扫码体验功能</div>
      </div>
      
      <button @click="handleShare">
        设置分享信息
      </button>

      <div class="instructions">
          <h3>使用说明：</h3>
          <ol>
              <li>使用QQ扫码或直接打开本页</li>
              <li>在QQ内置浏览器中打开页面</li>
              <li>点击右上角"•••"按钮</li>
              <li>选择"分享给好友"或"分享到QQ空间"</li>
              <li>分享的链接将显示为卡片样式</li>
          </ol>
      </div>
      
      <div class="status" v-html="status">
      </div>
      
      <div class="footer">
          注：此功能仅在QQ内置浏览器中有效
      </div>
  </div>
</template>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        font-family: 'PingFang SC', 'Microsoft YaHei', sans-serif;
    }
    
    body {
        display: flex;
        justify-content: center;
        align-items: center;
        min-height: 100vh;
        background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d);
        padding: 20px;
    }
    
    .container {
        background-color: rgba(255, 255, 255, 0.92);
        border-radius: 16px;
        box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        width: 100%;
        max-width: 500px;
        padding: 40px;
        text-align: center;
    }
    
    h1 {
        color: #333;
        margin-bottom: 20px;
        font-size: 28px;
        position: relative;
        padding-bottom: 15px;
    }
    
    h1:after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 25%;
        right: 25%;
        height: 3px;
        background: linear-gradient(to right, #1a2a6c, #fdbb2d);
        border-radius: 3px;
    }
    
    p {
        color: #555;
        margin-bottom: 30px;
        line-height: 1.6;
    }
    
    .qr-code {
        margin: 20px auto;
        padding: 15px;
        background: white;
        border-radius: 10px;
        display: inline-block;
        box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    }
    
    .qr-code img {
        width: 180px;
        height: 180px;
        display: block;
    }
    
    .qr-label {
        margin-top: 10px;
        font-size: 14px;
        color: #666;
    }
    
    .share-btn {
        background: linear-gradient(135deg, #12c2e9, #c471ed, #f64f59);
        color: white;
        border: none;
        padding: 16px 40px;
        font-size: 18px;
        font-weight: 600;
        border-radius: 50px;
        cursor: pointer;
        margin: 30px 0;
        box-shadow: 0 6px 20px rgba(198, 113, 237, 0.5);
        transition: all 0.3s ease;
        position: relative;
        overflow: hidden;
    }
    
    .share-btn:hover {
        transform: translateY(-3px);
        box-shadow: 0 8px 25px rgba(198, 113, 237, 0.7);
    }
    
    .share-btn:active {
        transform: translateY(1px);
    }
    
    .instructions {
        background-color: #f0f7ff;
        border-left: 4px solid #3498db;
        padding: 15px;
        margin: 25px 0;
        text-align: left;
        border-radius: 0 8px 8px 0;
    }
    
    .instructions h3 {
        color: #2980b9;
        margin-bottom: 10px;
    }
    
    .instructions ol {
        padding-left: 20px;
    }
    
    .instructions li {
        margin-bottom: 8px;
        color: #555;
    }
    
    .status {
        margin-top: 25px;
        padding: 15px;
        border-radius: 10px;
        background-color: #f8f9fa;
        font-size: 14px;
        color: #555;
    }
    
    .success {
        color: #27ae60;
        font-weight: bold;
    }
    
    .error {
        color: #e74c3c;
        font-weight: bold;
    }
    
    .footer {
        margin-top: 30px;
        color: #777;
        font-size: 13px;
    }
</style>
