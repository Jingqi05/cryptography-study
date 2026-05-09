# 密码学研究生研究方向

## 主要研究分支

```
密码学研究
├── 密码理论
│   ├── 可证明安全 (Provable Security)
│   ├── 形式化验证 (Formal Verification)
│   └── 复杂性理论
├── 密码工程
│   ├── 侧信道攻击与防护
│   ├── 硬件加速 (FPGA/ASIC)
│   ├── PQC 工程实现
│   └── 密码芯片设计
├── 密码协议
│   ├── 零知识证明 (ZKP)
│   ├── 安全多方计算 (MPC)
│   ├── 认证密钥协商 (AKA)
│   └── 区块链共识协议
├── 安全计算
│   ├── 全同态加密 (FHE)
│   ├── 可信执行环境 (TEE)
│   ├── 隐私保护机器学习 (PPML)
│   └── 安全联邦学习
└── 密码分析
    ├── 量子密码分析
    ├── 代数攻击
    └── 差分/线性分析
```

## 热门研究方向（2024-2025）

### 1. 后量子密码学（PQC）

**研究内容**：
- NIST PQC 标准算法的高效实现（ML-KEM, ML-DSA）
- 格密码的理论安全性证明
- 后量子 TLS 协议设计
- 混合密码方案（经典 + 后量子）

**关键词**：格密码、LWE/RLWE、CRYSTALS、后量子迁移

**代表论文**：
- CRYSTALS-Kyber: The CCA-Secure Module-Lattice-Based KEM
- CRYSTALS-Dilithium: A Lattice-Based Digital Signature Scheme

### 2. 零知识证明（ZKP）

**研究内容**：
- zk-SNARKs 效率优化
- zk-STARKs 透明性证明
- 递归证明组合
- ZK-Rollup（区块链扩容）

**关键词**：zk-SNARK、zk-STARK、Bulletproofs、Plonk、Groth16

**应用场景**：区块链隐私、身份匿名认证、可验证计算

### 3. 安全多方计算（MPC）

**研究内容**：
- 混合协议（GMW + OT + GC）
- 恶意安全 vs 半诚实安全
- MPC 协议的工程优化
- 隐私保护数据分析

**关键词**：混淆电路 (Garbled Circuit)、不经意传输 (OT)、秘密共享 (Secret Sharing)

### 4. 全同态加密（FHE）

**研究内容**：
- FHE 方案效率优化（CKKS, BFV, BGV）
- FHE 硬件加速器设计
- FHE 在机器学习中的应用
- 密态计算框架

**关键词**：CKKS、Bootstrapping、Lattice-based FHE

**挑战**：计算开销大（比明文慢 10^4~10^6 倍）

### 5. 侧信道攻击与防护

**研究内容**：
- 功耗分析攻击（SPA/DPA）
- 电磁辐射分析
- 时序攻击
- 故障注入攻击
- 掩码 (Masking) 和隐藏 (Hiding) 防护

**关键词**：DPA、EM Analysis、Fault Injection、Masking

### 6. 隐私保护机器学习（PPML）

**研究内容**：
- 联邦学习中的密码学保护
- 安全推理（Secure Inference）
- 差分隐私 + 密码学
- 可信 AI

**关键词**：联邦学习、安全推理、差分隐私、TEE+ML

## 国内密码学重点实验室

| 机构 | 方向 | 特色 |
|------|------|------|
| 清华大学 | 密码理论、ZKP | 顶会论文多 |
| 中科院信工所 | 密码工程、PQC | 国密标准制定 |
| 西安电子科技大学 | 密码学综合 | 密码学传统强校 |
| 上海交通大学 | MPC、FHE | 隐私计算方向 |
| 山东大学 | 密码理论 | 可证明安全 |
| 武汉大学 | 密码协议 | 软件安全 |

## 推荐学术资源

| 资源 | 说明 |
|------|------|
| [IACR ePrint](https://eprint.iacr.org/) | 密码学预印本，最新论文 |
| [CRYPTO/EUROCRYPT/ASIACRYPT](https://iacr.org/conferences/) | 密码学三大顶会 |
| [IEEE S&P/USENIX Security/CCS/NDSS](https://ieee-security.org/) | 安全四大顶会 |
| [CNKI 中国知网](https://cnki.net/) | 中文论文 |
| [国家密码管理局](http://www.oscca.gov.cn/) | 国密标准 |

## 研究生必备技能

| 技能 | 说明 |
|------|------|
| 数学基础 | 代数、数论、概率论、复杂性理论 |
| 编程能力 | C/C++、Python、Rust |
| 密码库使用 | OpenSSL、GmSSL、libsodium、mcl |
| 形式化工具 | ProVerif、Tamarin、CryptoVerif |
| 论文阅读 | IACR ePrint、顶会论文 |
| 实验能力 | 侧信道实验台、FPGA 开发 |
