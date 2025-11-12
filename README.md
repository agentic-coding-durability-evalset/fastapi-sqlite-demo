# FastAPI SQLite Demo

一个基于 [FastAPI](https://fastapi.tiangolo.com/) 和 SQLite 的 Python Web 应用示例项目。使用 SQLModel 作为 ORM，展示了如何构建现代化的异步 API。

## 技术栈

- **Python**: 3.13+
- **FastAPI**: 0.112.1+
- **SQLModel**: 0.0.27+ (基于 SQLAlchemy 和 Pydantic)
- **SQLAlchemy**: 2.0.41+
- **aiosqlite**: 0.21.0+ (异步 SQLite 驱动)
- **Pytest**: 8.4.2+ (测试框架)

## 项目结构

```
fastapi-sqlite-demo/
├── app/
│   ├── main.py              # FastAPI 应用入口
│   ├── dependencies.py      # 依赖注入
│   ├── domain/
│   │   ├── models.py        # 数据模型定义
│   │   ├── infra/
│   │   │   └── db.py        # 数据库连接配置
│   │   └── repository/
│   │       ├── hero_repo.py # Hero 数据仓库
│   │       └── tests/       # 仓库测试
│   └── routers/
│       └── heros.py         # Hero API 路由
├── db/
│   ├── schema.ddl          # 数据库模式定义
│   └── demo.sqlite3        # SQLite 数据库文件
├── tests/
│   └── test_sqlmodel.py   # 集成测试
├── pyproject.toml          # 项目配置和依赖
├── pytest.ini             # Pytest 配置
├── Dockerfile             # Docker 配置
├── Justfile               # Just 构建工具配置
└── README.md
```

## 功能特性

- RESTful API 设计
- 异步数据库操作
- SQLModel ORM (结合 SQLAlchemy 和 Pydantic)
- 自动 API 文档 (Swagger/OpenAPI)
- 依赖注入
- 单元测试和集成测试
- Docker 支持

## 快速开始

### 前置要求

- Python 3.13 或更高版本
- pip 或 uv (推荐)

### 安装和运行

```bash
# 创建虚拟环境（推荐）
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# 安装依赖
pip install -e ".[dev]"

# 运行应用
fastapi dev app/main.py
```

应用将在 `http://localhost:8000` 启动。

## API 端点

### 根路径
```http
GET http://localhost:8000/
```
响应: `{"message": "Hello World!"}`

### Hero API

所有 Hero 相关的 API 端点定义在 `/app/routers/heros.py` 中。

## 开发工具

### Just

项目包含 `Justfile`，提供便捷的命令：

```bash
# 查看可用命令
just

# 运行开发服务器
just dev

# 运行测试
just test
```

## 项目特点

### 领域驱动设计

项目采用领域驱动设计 (DDD) 结构：
- **Domain**: 业务逻辑和模型
- **Infrastructure**: 基础设施（数据库）
- **Repository**: 数据访问层
- **Routers**: API 路由层

### 依赖注入

使用 FastAPI 的依赖注入系统管理数据库会话等资源。

## 参考资源

- [FastAPI 文档](https://fastapi.tiangolo.com/)
- [SQLModel 文档](https://sqlmodel.tiangolo.com/)
- [Simple Hero API with FastAPI](https://sqlmodel.tiangolo.com/tutorial/fastapi/simple-hero-api/)
