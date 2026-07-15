# 约会邀请函

一份浪漫的互动式约会邀请页面，可直接部署到 GitHub Pages。

## 本地预览

用浏览器直接打开 `index.html`，或在项目目录运行：

```bash
python3 -m http.server 8080
```

然后访问 http://localhost:8080

## 自定义内容

打开 `index.html`，找到 `CONFIG` 对象，修改地点、文案、美食选项等内容即可。**美食类型和约会时间由打开链接的人自己选择**：

```javascript
const CONFIG = {
  name: "胡蝶",
  foodOptions: [
    { id: "hotpot", emoji: "🍲", name: "火锅", desc: "热气腾腾，一起涮好吃的" },
    { id: "bbq", emoji: "🍢", name: "烧烤", desc: "烟火气满满，边吃边聊" },
    // 可继续添加更多选项...
  ],
  // ...
};
```

## 部署到 GitHub Pages

1. 在 GitHub 新建仓库（例如 `date-invitation`）
2. 将本项目推送到仓库
3. 进入仓库 **Settings → Pages**
4. **Source** 选择 `Deploy from a branch`
5. **Branch** 选择 `main`，文件夹选择 `/ (root)`
6. 保存后等待几分钟，访问 `https://你的用户名.github.io/仓库名/`

## 邮件通知（Web3Forms）

胡蝶确认赴约后，选择内容会自动发到你的邮箱。使用 [Web3Forms](https://web3forms.com)（免费，对 QQ 邮箱更友好）。

### 配置步骤（约 1 分钟）

1. 打开 https://web3forms.com
2. 输入邮箱 `2013826057@qq.com`，点击 **Create Access Key**
3. 去 QQ 邮箱查收 **Web3Forms 验证邮件**（可能在垃圾箱），点击验证链接
4. 复制页面上的 **Access Key**
5. 填入 `index.html` 的 `CONFIG.web3formsAccessKey`，同步到 `docs/index.html` 后推送

```javascript
const CONFIG = {
  notifyEmail: "2013826057@qq.com",
  web3formsAccessKey: "你的 Access Key",
  // ...
};
```

若邮件发送失败，成功页会显示「复制约会信息」按钮作为备用。

## 功能

- 信封开启动画 + 玻璃质感卡片
- 三步流程：接受邀请 → 选择美食 → 选择时间
- 确认赴约后自动邮件通知邀请人
- 美食选项：火锅、烧烤、烤肉、日料、西餐、麻辣烫等
- 实时预览已选时间
- 蝴蝶飞舞特效 + 确认后满屏蝴蝶庆祝
- 电脑 / 手机自适应布局
