# HFD CLI Helper

Hugging Face 模型/数据集下载命令生成器 - Web 界面

## 功能

- 可视化生成 `hfd.sh` 下载命令
- 支持所有 hfd.sh 参数选项
- 实时预览生成的命令
- 一键复制命令

## 部署到 Cloudflare Pages

### 方法一：连接 Git 仓库

1. 将代码推送到 GitHub 仓库
2. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
3. 进入 **Workers & Pages** > **Create application** > **Pages**
4. 选择 **Connect to Git**
5. 授权并选择你的仓库
6. 构建设置（静态页面无需特殊设置）：
   - Build command: 留空
   - Build output directory: `/` (根目录)
7. 点击 **Save and Deploy**

### 方法二：直接上传

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com/)
2. 进入 **Workers & Pages** > **Create application** > **Pages**
3. 选择 **Upload assets**
4. 拖放 `index.html` 文件
5. 点击 **Deploy site**

### 方法三：使用 Wrangler CLI

```bash
# 安装 wrangler
npm install -g wrangler

# 登录
wrangler login

# 部署
wrangler pages deploy . --project-name=hfd-helper
```

## 本地运行

直接用浏览器打开 `index.html` 即可，或使用本地服务器：

```bash
# Python
python -m http.server 8080

# Node.js
npx serve .
```

## 使用说明

1. 输入仓库 ID（如 `gpt2` 或 `meta-llama/Llama-2-7b`）
2. 根据需要配置选项：
   - 文件过滤（include/exclude）
   - 认证信息（Gated Repo 需要）
   - 下载工具和参数
3. 复制生成的命令
4. 在终端运行命令前，先设置环境变量：
   ```bash
   export HF_ENDPOINT=https://hf-mirror.com
   ```

## hfd.sh 获取

```bash
wget https://hf-mirror.com/hfd/hfd.sh
chmod +x hfd.sh
```

## 相关链接

- [HF-Mirror](https://hf-mirror.com/)
- [hfd.sh 原始脚本](https://gist.github.com/padeoe/697678ab8e528b85a2a7bddafea1fa4f)
- [HF Token 设置](https://huggingface.co/settings/tokens)
