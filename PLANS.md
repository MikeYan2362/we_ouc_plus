# 海大智能助手应用开发计划

## 项目概述
本项目是一个基于UniApp框架开发的校园智能助手应用，采用前后端分离架构，旨在为海大学生提供便捷的校园服务。

## 技术栈
- 前端：UniApp + Vue3 + TypeScript
- 后端：FastAPI + Python
- 数据库：PostgreSQL
- 向量数据库：Milvus/Pinecone（用于RAG系统）
- 部署：Docker + Nginx

## 系统架构

### 前端架构
```
src/
├── pages/                 # 页面文件
│   ├── login/            # 登录注册页面
│   ├── chat/             # 聊天助手页面
│   ├── map/              # 智能地图页面
│   ├── canteen/          # 智能食堂页面
│   └── hospital/         # 智能医院页面
├── components/           # 公共组件
├── store/               # 状态管理
├── api/                 # API接口
├── utils/               # 工具函数
└── styles/              # 全局样式
```

### 后端架构
```
backend/
├── app/
│   ├── api/             # API路由
│   ├── core/            # 核心配置
│   ├── models/          # 数据模型
│   ├── schemas/         # Pydantic模型
│   ├── services/        # 业务逻辑
│   └── utils/           # 工具函数
├── database/            # 数据库配置
├── knowledge_base/      # 知识库管理
└── tests/               # 测试文件
```

## 功能模块设计

### 1. 用户认证模块
- 实现用户注册、登录、密码重置功能
- JWT token认证
- 用户信息管理

### 2. 智能聊天助手模块
- 基于RAG的问答系统
- 本地知识库管理
- 对话历史记录存储
- 实时对话功能

### 3. 智能地图模块
- 校园地图展示
- 建筑物信息查询
- 路径规划
- 实时位置共享

### 4. 智能食堂模块
- 食堂窗口信息展示
- 菜品信息管理
- 实时排队情况
- 用户评价系统

### 5. 智能医院模块
- 医院信息展示
- 预约挂号系统
- 医生信息管理
- 紧急联系方式

## 数据库设计

### 用户表 (users)
- id: 主键
- username: 用户名
- password_hash: 密码哈希
- email: 邮箱
- created_at: 创建时间
- last_login: 最后登录时间

### 聊天记录表 (chat_history)
- id: 主键
- user_id: 用户ID
- conversation_id: 会话ID
- message: 消息内容
- is_user: 是否用户消息
- created_at: 创建时间

### 食堂信息表 (canteen)
- id: 主键
- name: 食堂名称
- location: 位置
- operating_hours: 营业时间

### 菜品表 (dishes)
- id: 主键
- canteen_id: 食堂ID
- name: 菜品名称
- price: 价格
- description: 描述
- rating: 评分

## 开发计划

### 第一阶段：基础架构搭建
1. 项目初始化
2. 数据库设计
3. 用户认证系统
4. 基础UI框架

### 第二阶段：核心功能开发
1. 智能聊天助手
2. 知识库系统
3. 地图功能
4. 食堂信息管理

### 第三阶段：扩展功能开发
1. 医院信息管理
2. 评价系统
3. 实时数据更新
4. 性能优化

### 第四阶段：测试与部署
1. 单元测试
2. 集成测试
3. 性能测试
4. 部署上线

## 安全考虑
1. 用户数据加密
2. API访问控制
3. 防止SQL注入
4. XSS防护
5. CSRF防护

## 性能优化
1. 数据库索引优化
2. 缓存策略
3. 静态资源CDN
4. 代码分割
5. 懒加载

## 后续扩展
1. 更多校园服务集成
2. 个性化推荐
3. 社交功能
4. 活动管理
5. 成绩查询 