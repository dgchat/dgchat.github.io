# DGCHAT 🔐

**DGCHAT** 是一款基于 [Nostr](https://nostr.com/) 协议构建的、完全去中心化的全场景加密通讯端。它不需要电话号码、不需要电子邮件，甚至没有中心化服务器。你的身份就是你的密钥，你的通讯主权完全掌握在自己手中。

### 🌐 [立即在线使用](https://dgchat.github.io/)

---

## ✨ 核心特性

- **🛡️ 极致隐私**：无需注册。只需生成一对密钥即可开始聊天。身份完全匿名，无法被追踪或封禁。
- **🔒 军事级加密**：
  - **端到端加密**：支持标准的 NIP-04 和更高级的 NIP-59 (Gift Wrap) 协议，确保只有收发双方能读取内容。
  - **本地二次加密**：所有存储在浏览器本地的数据（私钥、聊天记录）均通过 WebCrypto API 使用用户自定义密码进行 AES-GCM 高强度加密。
- **👻 幽灵群组 (Ghost Groups)**：独创的共享密钥匿名群组。群成员共用一套派生私钥，实现物理层面的身份混淆。
- **☁️ 去中心化备份**：支持将通讯录、屏蔽名单和群组信息通过增量加密的方式备份到 Nostr 中继器，实现跨设备无缝漫游。
- **🚀 零后端架构**：纯 HTML/JavaScript 开发，无任何后端逻辑，可直接作为静态页面部署在 GitHub Pages、IPFS 或本地运行。
- **⚡ 闪电网络集成**：支持展示 Lud16 协议地址，方便在通讯过程中进行小额比特币打赏。

---

## 🛠️ 技术栈

- **协议**: [Nostr Protocol](https://github.com/nostr-protocol/nips) (Kind 0, 3, 4, 42, 1059 等)
- **加密库**: [libsodium.js](https://github.com/jedisct1/libsodium.js), [Nostr-tools](https://github.com/nbd-wtf/nostr-tools)
- **UI 框架**: [Tailwind CSS](https://tailwindcss.com/)
- **存储**: IndexedDB + LocalStorage (全加密缓存)

---

## 🚀 快速开始

1. **部署到自己的空间**：
   - Fork 本仓库。
   - 在仓库设置中开启 `GitHub Pages`。
   - 你的专属私密通讯站就建成了：`https://<你的用户名>.github.io/`
2. **本地运行**：
   - 下载 `index.html`。
   - 直接用浏览器打开即可使用。

---


## ⚠️ 安全警告

1. **私钥即一切**：DGCHAT 不存储你的任何私钥。如果你丢失了私钥且没有备份，你的账号和聊天记录将永远无法找回。
2. **本地密码**：本地登录密码仅用于解密本地存储。如果忘记该密码，你需要清除浏览器数据并重新导入私钥。
3. **中继器风险**：虽然消息是加密的，但元数据（谁在什么时候发了消息）可能被中继器记录。建议配合信任的私有中继器使用。

---

## ⚖️ 开源协议

本项目采用 [MIT License](LICENSE) 协议开源。你可以自由地分发、修改和自用。

---

**DGCHAT** - *隐私是基本人权，通讯自由属于每一个人。*

---

### ⚠️ 免责声明 (Disclaimer)

**使用本程序即表示您已阅读并同意以下条款：**

1.  **无担保声明**：本程序按“原样”（As-Is）提供，不附带任何形式的明文或暗示的保证。开发者不对程序的稳定性、准确性或安全性（包括但不限于数据丢失、系统崩溃、由于第三方节点导致的通讯中断等）承担责任。
2.  **数据与密钥安全**：**DGCHAT** 是一个纯客户端程序，开发者无法访问、存储或恢复您的任何私钥。**私钥丢失或泄露导致的任何后果（如身份被冒用、加密记录无法恢复等）完全由用户自行承担。**
3.  **合法使用**：用户承诺在遵守所在地法律法规的前提下使用本程序。开发者不对用户通过本程序发布的任何内容（文本、图片等）负责，亦不承担因用户违规使用而产生的任何法律责任。
4.  **技术局限性**：虽然程序采用了高强度加密，但在计算机领域没有绝对的安全性。用户应知晓中继器（Relay）可能记录元数据（如 IP 地址、在线时间等），并建议在高安全性要求的场景下配合 VPN 或自建中继器使用。
5.  **资产风险**：程序集成的闪电网络展示功能仅供参考，涉及任何数字资产（如比特币）的发送与接收均存在技术风险。开发者不对任何资产损失负责。

---

**By using this software, you agree to the following terms:**

1.  **As-Is Provision**: The software is provided "as is" without warranty of any kind. The developer assumes no liability for system failures, data loss, or communication interruptions caused by third-party relays.
2.  **Key Responsibility**: **DGCHAT** is a client-side only application. The developer has no access to your private keys. **You are solely responsible for the backup and security of your keys.** Loss of keys results in permanent loss of access.
3.  **Compliance**: Users are responsible for ensuring their use of this software complies with local laws and regulations. The developer does not monitor or control the content transmitted and is not liable for user-generated content.
4.  **Metadata Risk**: Users should be aware that while messages are encrypted, third-party relays may still log metadata (e.g., IP addresses).
5.  **Financial Risk**: Any use of integrated Lightning Network features is at the user's own risk. The developer is not responsible for any loss of digital assets.

---
