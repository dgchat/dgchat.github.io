# DGCHAT 🔐

**DGCHAT** 是一款基于 [Nostr](https://nostr.com/) 协议构建的去中心化加密通讯客户端。

无需电话号码、电子邮件或传统账号注册。用户通过密码学密钥建立身份，使用去中心化中继网络进行通讯。

DGCHAT 致力于提供简洁、自由、注重隐私的通讯体验。除基础聊天功能外，也提供群组交流、跨设备数据同步以及轻量化的数字资产管理与转账功能。

### 🌐 [立即在线使用](https://dgchat.github.io/)

---

## ✨ 核心特性

- **🛡️ 隐私优先**：无需传统账号注册，通过 Nostr 密钥建立身份。用户自主保管私钥，减少对中心化账号系统的依赖。

- **🔒 端到端加密**：
  - **加密通讯**：支持 NIP-04 和 NIP-59（Gift Wrap）等 Nostr 协议机制，保护私聊内容。
  - **本地数据保护**：使用 WebCrypto API 和本地密码加密保护账户私钥，并对聊天缓存等敏感数据提供本地加密存储。
  - **自动锁定**：支持自定义无操作锁定时间，锁定后清除当前会话中的私钥，重新使用时需输入本地密码。

- **👻 幽灵群组（Ghost Groups）**：基于共享密钥的群组通讯机制，提供区别于传统公开群组的交流方式。

- **☁️ 去中心化数据备份**：支持将通讯录、群组设置及部分个人配置以加密形式备份至 Nostr 中继网络，方便在不同设备之间恢复和同步。

- **💬 便捷通讯体验**：
  - 支持文字、图片及常用消息操作。
  - 支持好友管理、个人资料和群组管理。
  - 支持消息状态查看与本地聊天记录管理。
  - 适配电脑与手机浏览器。

- **₿ 轻量化 NBTC 钱包**：内置独立的 NBTC 管理界面，可查看地址、查询余额、管理转账及浏览交易记录。支持在好友资料中查看对方的 NBTC 地址，并快速发起转账。相关链上数据通过独立的索引服务查询。

- **⚡ 闪电网络支持**：支持 Lightning Address（LUD16）及 Nostr Wallet Connect（NWC），可连接兼容的外部闪电钱包，在好友之间发起小额闪电网络付款。付款由用户授权的外部钱包执行，相关功能仍处于持续测试和完善阶段。

- **🚀 单文件客户端**：基于 HTML、JavaScript 和 CSS 构建，主要通讯与界面逻辑均在浏览器中运行。无需部署专属聊天后台，可通过静态网站托管，也可下载 HTML 文件在兼容的浏览器环境中使用。

---

## 🛠️ 技术栈

- **通讯协议**：[Nostr Protocol](https://github.com/nostr-protocol/nips)（NIP-04、NIP-17/59 等）
- **加密组件**：[libsodium.js](https://github.com/jedisct1/libsodium.js)、[Nostr-tools](https://github.com/nbd-wtf/nostr-tools)、WebCrypto API
- **界面技术**：HTML5、JavaScript、[Tailwind CSS](https://tailwindcss.com/)
- **本地存储**：IndexedDB、LocalStorage、SessionStorage
- **数字资产支持**：[NBTC 钱包](https://nextbtc.rf.gd)、Lightning Address、LNURL-pay、Nostr Wallet Connect
- **部署方式**：静态网页托管或单 HTML 文件运行

---

## 🚀 快速开始

### 1. 在线使用

直接访问：

**https://dgchat.github.io/**

首次使用时，可创建新的 Nostr 身份，也可以导入已有私钥。

按照页面提示设置本地密码，即可开始使用。

### 2. 自行部署

1. Fork 本仓库。
2. 在仓库设置中启用 `GitHub Pages`。
3. 根据 GitHub Pages 的说明配置发布分支。
4. 使用分配的域名访问自己的 DGCHAT 页面。

### 3. 本地运行

1. 下载仓库中的 `index.html`。
2. 使用支持现代 JavaScript 和 WebCrypto API 的浏览器打开。
3. 创建或导入账号。

部分浏览器对本地文件的存储、加密和网络访问存在限制。如果相关功能无法正常使用，建议通过 HTTPS 静态网站访问。

### 4. 可选功能

DGCHAT 的基本通讯功能不依赖 NBTC 或 Lightning 钱包。

如需使用相关功能，可自行配置 NBTC 索引服务，或连接支持 NWC 的外部 Lightning 钱包。

---

## ⚠️ 安全提示

1. **私钥管理**：Nostr 私钥是账户身份的重要凭据。请妥善离线备份，不要发送给他人。私钥遗失可能导致无法恢复原有身份。

2. **本地密码**：本地密码用于保护浏览器保存的账户数据。遗忘密码时，可能需要重新导入已备份的私钥。

3. **会话安全**：DGCHAT 支持在有效登录会话内刷新页面并恢复登录。自动锁定或手动锁定后，需要重新输入密码。建议不要在不可信设备上长期保持登录状态。

4. **中继网络**：Nostr Relay 负责转发消息。虽然私聊内容经过加密处理，但连接 IP、通信时间及部分协议元数据仍可能被第三方观察或记录。

5. **本地数据**：清理浏览器存储、使用隐私模式或更换设备，可能导致本地缓存和配置丢失。建议定期备份必要信息。

6. **资产操作**：NBTC 与 Lightning 相关功能均涉及真实数字资产。请仔细核对收款地址、金额和付款信息。相关操作可能不可撤销。

7. **钱包授权**：使用 NWC 连接外部 Lightning 钱包时，建议在钱包端设置适当的授权额度，避免授予不必要的资金操作权限。

---

## ⚖️ 开源协议

本项目采用 [MIT License](LICENSE) 协议开源。

允许在遵守许可证条款的前提下自由使用、修改与分发。

---

**DGCHAT** — *隐私是基本人权，通讯自由属于每一个人。*

---

## ⚠️ 免责声明（Disclaimer）

**使用本程序即表示您已阅读并理解以下条款：**

1. **无担保声明**：本程序按“原样”（As-Is）提供，不附带任何形式的明示或暗示保证。开发者不保证程序在所有设备、浏览器、网络环境或第三方服务中均能正常运行。

2. **数据与密钥安全**：DGCHAT 主要作为客户端程序运行，开发者不通过专属中心化聊天后台托管用户私钥。用户应自行妥善保存私钥、本地密码及必要的数据备份。私钥遗失、泄露或设备故障可能导致身份、聊天记录或相关资产无法恢复。

3. **合法使用**：用户应遵守所在地适用的法律法规。用户对使用本程序产生、发送或保存的内容及相关行为自行承担责任。

4. **技术局限性**：任何密码学实现或通信系统都无法保证绝对安全。Nostr Relay、网络服务提供商及其他第三方基础设施可能记录连接信息或部分通信元数据。

5. **第三方服务**：本程序部分功能依赖 Nostr Relay、区块链索引服务、Lightning 钱包及其他外部服务。这些服务的可用性、安全性和运行规则不受 DGCHAT 控制。

6. **资产风险**：NBTC 和 Lightning 功能仅作为客户端辅助工具提供。数字资产转账可能涉及交易失败、网络延迟、手续费、错误收款地址、第三方服务故障及资金损失等风险。用户应自行核对交易信息，并在充分理解风险后使用相关功能。

7. **责任范围**：在适用法律允许的范围内，开发者不对因使用或无法使用本程序而产生的数据丢失、通讯中断、资产损失及其他直接或间接损害承担责任。

---

**By using this software, you acknowledge the following terms:**

1. **As-Is Provision**: DGCHAT is provided on an "as-is" basis, without warranties of any kind. Compatibility, reliability, availability, and security are not guaranteed.

2. **Key Responsibility**: Users are responsible for safeguarding their private keys, local passwords, and backups. The developer does not operate a centralized key-recovery service.

3. **Compliance**: Users are responsible for complying with applicable laws and regulations and for the content and activities associated with their use of the software.

4. **Metadata Risk**: Encrypted communication does not guarantee complete anonymity. Third-party Nostr relays and network providers may observe connection information or communication metadata.

5. **Third-Party Services**: Certain functions depend on independent relays, blockchain index services, Lightning wallets, or other external infrastructure beyond the developer's control.

6. **Financial Risk**: NBTC and Lightning Network features may involve real digital assets. Transactions can be irreversible, and users are solely responsible for verifying payment details and understanding the associated risks.

7. **Limitation of Liability**: To the extent permitted by applicable law, the developer shall not be liable for losses or damages arising from the use of or inability to use the software.

---

**DGCHAT** — *Privacy matters. Communication should remain free.*
