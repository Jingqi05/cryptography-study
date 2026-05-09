# 密码学应用

## TLS/HTTPS

TLS（Transport Layer Security）是最广泛使用的密码学协议。

### TLS 1.3 握手流程

```
客户端                                服务器
  │                                    │
  │── ClientHello ────────────────────>│
  │   支持的密码套件                    │
  │   密钥共享 (ECDHE + ML-KEM)         │
  │                                    │
  │<── ServerHello ───────────────────│
  │   选择的密码套件                    │
  │   密钥共享                         │
  │   证书 + 签名                      │
  │   Finished                         │
  │                                    │
  │── Finished ──────────────────────>│
  │                                    │
  │   ═══ 握手完成 ═══                 │
  │   使用派生密钥加密通信              │
  │   AES-256-GCM / ChaCha20-Poly1305 │
```

### TLS 密码套件

```
TLS_AES_256_GCM_SHA384
│   │     │      │
│   │     │      └── 哈希算法
│   │     └──────── 工作模式
│   └────────────── 对称加密算法
└────────────────── 协议
```

## PKI 证书体系

### 信任链

```
根 CA (Root CA)
  │ 自签名证书，预装在操作系统/浏览器
  │
  ▼
中间 CA (Intermediate CA)
  │ 由根 CA 签发
  │
  ▼
终端实体证书 (End-entity)
  │ 由中间 CA 签发
  │
  ▼
网站/应用
```

### Let's Encrypt

- 免费、自动化证书颁发
- ACME 协议
- 90 天有效期，自动续期

## 区块链密码学

### 比特币

```
交易签名：ECDSA (secp256k1)
地址生成：SHA-256 + RIPEMD-160
工作量证明：SHA-256 双重哈希
Merkle Tree：SHA-256
```

### 以太坊

```
交易签名：ECDSA (secp256k1)
地址生成：Keccak-256
智能合约：Keccak-256
```

## SSH 安全连接

### SSH 密钥认证

```
客户端                                服务器
  │                                    │
  │── 公钥认证请求 ──────────────────>│
  │                                    │
  │<── 随机挑战 ─────────────────────│
  │                                    │
  │── 私钥签名(挑战) ──────────────>│
  │                                    │
  │<── 认证成功 ────────────────────│
```

### SSH 密钥类型

| 类型 | 算法 | 推荐 |
|------|------|------|
| ssh-rsa | RSA | ⚠️ 逐步淘汰 |
| ssh-ed25519 | Ed25519 | ✅ 推荐 |
| ecdsa-sha2-nistp256 | ECDSA | ✅ 可用 |

## JWT 令牌

### JWT 结构

```
Header.Payload.Signature

Header:  {"alg":"ES256","typ":"JWT"}
Payload: {"sub":"user123","exp":1700000000}
Signature: ECDSA(header + payload, 私钥)
```

### 签名算法选择

| 算法 | 类型 | 推荐 |
|------|------|------|
| HS256 | HMAC-SHA256 | ⚠️ 共享密钥 |
| RS256 | RSA-PKCS1 | ✅ |
| ES256 | ECDSA P-256 | ✅ 推荐 |
| EdDSA | Ed25519 | ✅ 最佳 |

## 密码学最佳实践

### ✅ 应该做的

- 使用 AEAD 加密（AES-GCM, ChaCha20-Poly1305）
- 使用 ECDHE 实现前向保密
- 使用慢哈希存储密码（Argon2, bcrypt）
- 定期轮换密钥
- 使用 TLS 1.3
- 验证证书链

### ❌ 不应该做的

- 自己实现密码算法
- 使用 ECB 模式
- 使用 MD5/SHA-1 做安全用途
- 用 Random 生成密钥（用 RandomNumberGenerator）
- 在日志中记录密钥
- 忽略证书验证错误
