# 工具经验 TOOLS

## 飞书 CLI (lark-cli)

### 已确认能力
- ✅ 知识库（Wiki）空间创建、删除、列表查询
- ✅ 知识库节点创建、列表查询、删除
- ✅ 多维表格（Base）创建
- ✅ 多维表格表创建、重命名、字段增删
- ✅ 多维表格记录批量创建、查询、搜索
- ✅ 云文档创建、Markdown 导入
- ✅ 用户身份授权（--as user）
- ✅ Bot 身份操作（--as bot）
- ✅ 机器人信息设置（名字、头像）
- ✅ 云盘文件删除

### 使用经验

**日期：2026-08-09**
- **工具**：lark-cli base
- **任务**：创建多维表格及字段
- **注意事项**：
  - `+field-create` 的 `--json` 参数是字段属性 JSON，输出格式用 `--format json`
  - 不要同时用两个 `--json`，会冲突
  - 字段类型：text=文本、select=单选、user=人员、datetime=日期、attachment=附件
  - 单选/多选字段传 options 数组
  - 人员字段 type 为 "user"
  - `+field-delete` 是 high-risk-write，需要 `--yes`
  - 表至少保留 1 个字段，无法全部删完

**日期：2026-08-09**
- **工具**：lark-cli wiki
- **任务**：创建知识库和节点
- **注意事项**：
  - `+space-create` 创建知识库空间
  - `+node-create` 支持 `--parent-node-token` 创建子节点
  - `--obj-type docx` 创建文档节点
  - 返回的 node_token 用于节点操作，obj_token 用于文档内容操作

### 已知问题
- 飞书自动化工作流 API 未开放（返回 404），需手动在界面配置
- 多维表格公式字段 API 不支持复杂配置，需手动添加
- 飞书"从消息列表移除/标记已完成"无公开 API 支持，需手动操作

### 安全提醒
本页面只记录工具使用经验和方法，**不存储**：
- App Secret
- Access Token
- Refresh Token
- 密码
- Cookie
- 其他敏感凭证
