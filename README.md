<!--
  ╔══════════════════════════════════════════════════════════════════╗
  ║  JiliTech · Oral Muscle Rehabilitation Platform                 ║
  ║  肌力科技 · 口腔肌肉功能康复平台                                    ║
  ║  GitHub README — EN/CN Bilingual                                ║
  ╚══════════════════════════════════════════════════════════════════╝
-->

# 🦷 JiliTech — Oral Muscle Rehabilitation Platform
# 🦷 肌力科技 — 口腔肌肉功能康复平台

> **AI-powered wearable EMG sensor + WeChat Mini Program — professional oral muscle training at home.**
>
> **AI 驱动的可穿戴肌电传感器 + 微信小程序，在家即可完成专业级口腔肌肉训练。**

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Vue 3](https://img.shields.io/badge/Vue-3.x-4FC08D?logo=vue.js)](https://vuejs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript)](https://www.typescriptlang.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-Python%203.10-009688?logo=fastapi)](https://fastapi.tiangolo.com)
[![WeChat MiniProgram](https://img.shields.io/badge/WeChat-MiniProgram-07C160?logo=wechat)](https://developers.weixin.qq.com)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?logo=springboot)](https://spring.io/projects/spring-boot)
[![BLE](https://img.shields.io/badge/BLE-5.0-0082FC?logo=bluetooth)](https://www.bluetooth.com)

📡 Website / 官网: **[bymusclepower.com](https://bymusclepower.com/)** · 🏢 肌力（西安）医疗科技有限责任公司 · 📱 公众号: **知力智见**

---

## 🚀 What We Build · 我们的产品

**JiliTech** develops the world's first consumer-grade tongue & lip muscle EMG monitor paired with an intelligent training ecosystem — from BLE wearable hardware through WeChat Mini Program to clinical backend.

**肌力科技** 打造全球首款消费级舌唇肌电监测设备，配合智能训练生态——从 BLE 可穿戴硬件到微信小程序，再到临床数据后台，一站式覆盖。

```
[ EMG Wearable Sensor ] ──BLE──▶ [ WeChat Mini Program ] ──HTTP──▶ [ Clinical Backend ]
  100ms 实时数据采集                   居家训练 · AI 反馈                  医生工作站 · 数据分析
```

| User · 用户 | Need · 需求 | Scenario · 场景 |
|---|---|---|
| 👶 Children's parents / 儿童家长 | Training compliance monitoring / 训练依从性监控 | Orthodontic / 口腔正畸 |
| 🤕 Facial palsy adults / 面瘫成人 | Rehabilitation progress tracking / 康复进展追踪 | Neurology / 神经康复 |
| 🏥 Post-surgery patients / 术后患者 | Remote exercise guidance / 远程训练指导 | Oral surgery / 口腔外科 |
| 👨‍⚕️ Dentists & Therapists / 牙医与治疗师 | Patient management + data analysis / 患者管理与数据分析 | Clinical / 临床诊疗 |

---

## 🏗️ System Architecture · 系统架构

**4 web sub-systems** + **1 WeChat Mini Program** + **1 BLE hardware device** — full-stack medical rehabilitation platform.

**4 个 Web 子系统** + **1 个微信小程序** + **1 个 BLE 硬件设备** — 全栈医疗康复平台。

```
┌─────────────────────────────────────────────────────────────────┐
│                     ADMIN LAYER · 管理后台层                        │
│  jl-ui-admin-second          jl-data-ui-second                  │
│  运营管理后台                   企业数据平台                          │
│  Vue3 + Yudao (Lite)         Vue3 + Yudao (Full) · 852 views   │
└───────────────────────┬─────────────────────────────────────────┘
                        │
┌───────────────────────▼─────────────────────────────────────────┐
│                   CLINICAL LAYER · 临床工作站层                     │
│                   jl-pc-second                                  │
│                   医生 PC 工作站                                   │
│         Vben Admin 5.1 · WebSocket Real-time EMG               │
└───────────────────────┬─────────────────────────────────────────┘
                        │
┌───────────────────────▼─────────────────────────────────────────┐
│                    DATA LAYER · 影像数据层                         │
│                   jl_data_center                                │
│                   医学影像中心                                      │
│        FastAPI + Vue3 · DICOM / CBCT / MRI / 3D Recon         │
└─────────────────────────────────────────────────────────────────┘
```

---

## ✨ Key Features · 核心功能

### 🎯 Real-time EMG Measurement · 实时肌电测量
- **WebSocket** streaming at **100ms** sampling interval / **100ms** 采样间隔实时数据流
- Simultaneous dual-device measurement (tongue tip + lip muscle) / 双通道同步测量（舌尖 + 唇肌）
- Live ECharts visualization with automatic annotation / ECharts 实时曲线 + 自动标注
- 3 annotation algorithms: `lie_max_point` · `line_rising_slope` · `line_apf` (APF area) / 三种标注算法：最大值点 · 上升斜率 · APF 面积

### 📱 WeChat Mini Program (Patient Side) · 微信小程序（患者端）
- BLE device pairing & guided training sessions / BLE 设备配对 + 引导式训练课程
- Personalized training plans with AI feedback / 个性化训练计划 + AI 实时反馈
- Training compliance monitoring (daily / weekly trends) / 训练依从性监控（日/周趋势）
- Progress photo management (9-grid layout) / 训练照片管理（九宫格布局）

### 🏥 Doctor Workstation (`jl-pc-second`) · 医生工作站
- Patient full-lifecycle management: create → diagnose → train → archive / 患者全生命周期管理：建档→诊断→训练→归档
- 4-step intake form with clinical diagnosis multi-select / 四步接诊表 + 临床诊断多选
- **HIS integration** for patient import / **HIS 系统对接** 一键导入患者
- Doctor–patient messaging with training advice timeline / 医患消息 + 训练建议时间线
- Multi-record comparison: EMG, facial scan, intraoral scan (up to 5 records) / 多记录对比：肌力曲线、面部扫描、口内扫描（最多 5 条）

### 📊 Enterprise Data Platform (`jl-data-ui-second`) · 企业数据平台
- Patient cohort management with multi-dimensional filtering / 患者队列管理 + 多维度筛选
  - Age group · Region · Clinic · Gender · Annotation value range (`eq / gt / lt`) / 年龄段 · 区域 · 诊所 · 性别 · 标注值范围
- **Dual tag/annotation system** / **标签/标注双类型系统**
  - Labels (`type=2`) for classification / 标签用于分类
  - Annotations (`type=1`) with algorithm + span for clinical analysis / 标注含算法+跨度，用于临床分析
- 6-age-group stratification & reference range management / 六段年龄分层 + 参考区间管理
- 3 export types: measurement / training / user data / 三种数据导出：测量数据 / 训练数据 / 用户数据
- Filtered moving average: `filtered[i] = (data[i-1] + data[i] + data[i+1]) / 3` / 滤波移动平均

### 🖼️ Medical Imaging Center (`jl_data_center`) · 医学影像中心
- DICOM / CBCT / MRI medical imaging viewer / DICOM / CBCT / MRI 医学影像阅片
- Intraoral scan & facial 3D scan support / 口内扫描 + 面部三维扫描
- 3D reconstruction pipeline / 三维重建流水线
- MinIO object storage integration / MinIO 对象存储集成

---

## 🛠️ Tech Stack · 技术栈

| Layer · 层次 | Technology · 技术选型 |
|---|---|
| Frontend framework / 前端框架 | Vue 3 + TypeScript + Vite |
| UI library / UI 组件库 | Element Plus / Ant Design Vue |
| State management / 状态管理 | Pinia |
| Charts / 图表 | ECharts 5.x |
| Admin backend base / 管理后台基座 | Yudao (`yudao-ui-admin-vue3`) |
| Doctor workstation / 医生工作站 | Vben Admin 5.1 |
| Data API backend / 数据接口后端 | FastAPI (Python 3.10) |
| Object storage / 对象存储 | MinIO |
| Real-time communication / 实时通信 | WebSocket (EMG streaming) |
| Brand theme / 品牌主色 | `#bb1b20` (JL signature red / JL 品牌红) |

---

## 📐 Data Specification · 数据规格

```
Measurement data density / 测量数据密度 : 1 point / 100ms  (舌唇肌力)
Training data density    / 训练数据密度 : 1 point / 10ms   (训练传感器)
Unit conversion          / 单位换算     : value(g) × 0.00981 = N (牛顿)
X-axis time interval     / X轴时间间隔   : index × 0.1 = seconds (秒)
Training alert threshold / 训练预警阈值  : < 600s → flagged red #a90000 (标红)
```

---

## 📁 Project Structure · 项目结构

```
jilitech-platform/
├── jl-ui-admin-second/      # Ops Management Backend · 运营管理后台
│   └── src/views/jl/        # 8 custom medical business modules · 8个定制医疗业务模块
├── jl-pc-second/            # Doctor Workstation · 医生工作站
│   └── src/views/dashboard/ # 79 custom views · WebSocket EMG module
├── jl-data-ui-second/       # Enterprise Data Platform · 企业数据平台
│   ├── src/api/jl/data/     # JlDataApi — 22 custom API methods · 22个定制API方法
│   ├── src/views/child/     # Patient detail: measure / train / images · 患者详情
│   └── src/views/iot/       # Global data lists · Tag & annotation management
└── jl_data_center/          # Medical Imaging Center · 医学影像中心
    ├── main.py               # FastAPI app entry · 应用入口
    └── src/views/            # DICOM · 3D reconstruction viewer · 影像阅片
```

---

## 🔌 API Overview · API 概览

### JL Data Platform / 肌力数据平台 (`/jidongli/*`)

| Method | Endpoint | Description · 说明 |
|---|---|---|
| GET | `/jidongli/countJiliBusinessData` | Dashboard statistics (5 metrics) / 首页5项统计 |
| GET | `/jidongli/pageJilihuanzhe` | Patient paginated list / 患者分页列表 |
| GET | `/jidongli/getHuanzheCeli` | Measurement data by batch / 按批次查询测量数据 |
| GET | `/jidongli/getHuanzheTrain` | Training data by month / 按月查询训练数据 |
| GET | `/jidongli/pageHuanzheCeli` | Global measurement list (tag/annotation filter) / 测量数据全局列表 |
| GET | `/jidongli/pageHuanzheTrain` | Global training list / 训练数据全局列表 |
| POST | `/jidongli/annotateData` | Add clinical annotation / 添加临床标注 |
| POST | `/jidongli/addTagsToData` | Add tag to data record / 为数据添加标签 |
| POST | `/jl/user-file/create` | Upload patient photo / 上传患者图片 |
| GET | `/jidongli/exportJl{Celi,Train,User}Data` | Export dataset (3 types) / 数据导出（3种） |

---

## 🎯 Clinical Use Cases · 典型临床场景

```
Patient Journey · 患者就诊流程:

  Register           Initial Assessment        Device Pairing        Home Training
  患者建档              初诊评估                   设备配对               居家训练
     ↓                     ↓                        ↓                     ↓
  Doctor intake        EMG baseline             BLE connection        Daily sessions
  医生接诊录入         肌电基线测量               BLE 连接               每日训练
  (4-step form)                                                                 ↓
                                                                      Doctor Review
                                                                      医生复诊审核
                                                                      (Progress charts
                                                                       + Annotations)
```

**Target Clinical Areas · 目标临床领域:** Orthodontics · Facial Palsy · TMJ Disorders · Post-surgical Rehabilitation · Pediatric Orofacial Myology
**覆盖科室：** 正畸科 · 面瘫/神经内科 · 颞下颌关节 · 口腔外科术后 · 儿童口面肌功能

---

## 🏢 About JiliTech · 关于肌力科技

**肌力（西安）医疗科技有限责任公司** (JiliTech) is a medical-tech startup dedicated to **oral muscle function rehabilitation**. Our mission:

**肌力科技** 是一家专注于 **口腔肌肉功能康复** 的医疗科技创业公司。我们的使命：

> *Enable every patient to receive professional-grade muscle rehabilitation therapy without leaving home.*
>
> *让每一位患者都能在家享受专业级肌功能康复治疗。*

| Item · 事项 | Details · 详情 |
|---|---|
| 🌐 Website / 官网 | [bymusclepower.com](https://bymusclepower.com/) |
| 📍 Location / 所在地 | Xi'an, China · 中国西安 |
| 📱 WeChat Official Account / 微信公众号 | **知力智见** |
| 🎯 Market / 目标市场 | Orthodontics · Facial palsy · TMJ · Post-surgical rehab |
| 🔬 Research / 科研合作 | Joint research with university dental programs / 与高校口腔医学院联合研究 |
| 📈 Data Asset / 数据资产 | Multi-age-group muscle force reference ranges (0–3 / 3–12 / 12–20+) / 多年龄段肌力参考区间 |
| 🏥 Deployment / 部署方式 | SaaS + private deployment for dental clinics / SaaS + 口腔诊所私有化部署 |

---

## 🗺️ Roadmap · 路线图

- [x] **Phase 1** — Core EMG measurement + WeChat Mini Program / 核心肌电测量 + 微信小程序
- [x] **Phase 2** — Doctor workstation + data management platform / 医生工作站 + 数据管理平台
- [x] **Phase 3** — Medical imaging center (DICOM / 3D reconstruction) / 医学影像中心
- [ ] **Phase 4** — AI-powered training plan generation / AI 训练计划生成
- [ ] **Phase 5** — SaaS data licensing for research partners / 科研数据授权平台
- [ ] **Phase 6** — International expansion (EN localization) / 国际化拓展

---

## 📄 License · 开源协议

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

本项目基于 MIT 协议开源 — 详见 [LICENSE](LICENSE) 文件。

---

## 🤝 Contributing · 参与贡献

We welcome contributions from / 欢迎以下领域贡献者:

- 🦷 Dental / orthodontic clinicians — dataset labeling & clinical validation / 口腔正畸临床医师 — 数据标注与临床验证
- 💻 Frontend engineers — medical-grade data visualization & mini-program development / 前端工程师 — 医疗级数据可视化与小程序开发
- 🔬 Researchers — oral motor function, pediatric orofacial myology / 科研人员 — 口腔运动功能、儿童口面肌学

Please read our contributing guidelines before submitting a PR. / 提交 PR 前请阅读贡献指南。

---

## 📬 Contact & Community · 联系我们

<table>
  <tr>
    <td align="center" width="240">
      <img src="./assets/jilitech-wechat-qr.png" width="200" alt="知力智见公众号二维码" /><br/>
      <sub>📱 扫码关注公众号「知力智见」<br/>Follow us on WeChat</sub>
    </td>
    <td valign="top" style="padding-left:32px">
      <ul>
        <li>🐛 <strong>Bug Reports / Feature Requests</strong> / 问题反馈与功能建议: <a href="../../issues">GitHub Issues</a></li>
        <li>💼 <strong>Clinical Partnership</strong> / 临床合作: 公众号「知力智见」后台留言</li>
        <li>🔬 <strong>Research Collaboration</strong> / 科研协作: 数据集授权 &amp; 联合发表，欢迎垂询</li>
        <li>🏥 <strong>Clinic Deployment</strong> / 诊所部署: 提供 SaaS 订阅 &amp; 私有化部署方案</li>
        <li>🌐 <strong>Website</strong> / 官网: <a href="https://bymusclepower.com/">bymusclepower.com</a></li>
      </ul>
    </td>
  </tr>
</table>

---

<p align="center">
  <strong>JiliTech · 让每一位患者都能在家享受专业级肌功能康复</strong><br>
  <em>Bringing professional oral muscle rehabilitation to every home</em><br><br>
  <img src="./assets/jilitech-wechat-qr.png" width="120" alt="知力智见 公众号二维码" /><br>
  <sub>扫码关注 · 知力智见</sub>
</p>
