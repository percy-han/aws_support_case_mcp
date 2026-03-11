# 安装uv
##Ubuntu OS
curl -LsSf https://astral.sh/uv/install.sh | sh
source $HOME/.local/bin/env

## 创建虚拟环境（默认会生成 `.venv` 目录）
uv venv

## 激活虚拟环境（根据操作系统选择命令）
# Linux/macOS
source .venv/bin/activate


# 克隆mcp源代码
git clone https://github.com/percy-han/aws_support_case_mcp.git
cd aws_support_case_mcp/
export PYTHONPATH=$PYTHONPATH:$(pwd)

## 安装包
# 假设你已经安装了 uv
uv pip install -r requirements.txt

# 运行MCP 服务
FASTMCP_HOST="0.0.0.0" FASTMCP_PORT=8080 FASTMCP_STATELESS_HTTP=true python3 -m awslabs.aws_support_mcp_server.server

