### 项目架构
my-web-project/
├── frontend/                # 🎨 前端工程 (TS + HTML/CSS)
│   ├── public/              # 不参与编译的静态资源 (favicon, robots.txt)
│   ├── src/
│   │   ├── assets/          # 参与编译的资源 (图片, 字体, 全局CSS)
│   │   │   ├── styles/      # CSS/SCSS/Less 文件
│   │   │   └── images/
│   │   ├── api/             # 🔌 API 请求封装 (fetch/axios)
│   │   │   ├── client.ts    # HTTP 客户端实例 & 拦截器
│   │   │   └── modules/     # 按业务拆分的接口定义
│   │   ├── components/      # 可复用 UI 组件 (Web Components / Lit / 原生)
│   │   ├── pages/           # 页面级模块 (对应路由)
│   │   ├── utils/           # 纯函数工具库
│   │   ├── types/           # 📘 TypeScript 类型定义 (.d.ts)
│   │   ├── app.ts           # 应用入口逻辑
│   │   └── index.html       # SPA 入口模板
│   ├── dist/                # ⚙️ 构建产物 (部署用)
│   ├── vite.config.ts       # 构建配置 (推荐 Vite)
│   ├── tsconfig.json        # TS 编译选项
│   ├── package.json
│   └── .env.development     # 前端环境变量
│
├── backend/                 # 🐍 Python 后端工程
│   ├── app/
│   │   ├── api/             # 路由层 (Router/Blueprint)
│   │   │   └── v1/          # API 版本控制
│   │   ├── core/            # 核心配置 (安全, 数据库连接, 依赖注入)
│   │   ├── models/          # ORM 模型 / 数据库表结构
│   │   ├── schemas/         # Pydantic / Marshmallow 数据校验
│   │   ├── services/        # 💼 业务逻辑层
│   │   ├── repositories/    # 数据访问层 (可选, 复杂项目建议加)
│   │   └── main.py          # 应用启动入口
│   ├── tests/               # pytest 测试用例
│   ├── alembic/             # 数据库迁移脚本 (如用 SQLAlchemy)
│   ├── requirements.txt     # 或 pyproject.toml / poetry.lock
│   └── .env                 # 后端敏感配置
│
├── docker-compose.yml       # 🐳 一键启动前后端 + 数据库
├── Makefile                 # 常用命令快捷方式
├── .gitignore
└── README.md