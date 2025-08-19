<img width="2429" height="1631" alt="项目" src="https://github.com/user-attachments/assets/6fb89a04-b934-4128-8610-dc32a8a6c5a0" />

# Django-
Django课程教学平台是一个基于Django框架开发的一站式教学解决方案，专为教育场景设计。平台采用高效的全栈开发模式（前后端不分离），集课程管理、作业系统、考试评测、学习统计四大核心功能于一体，为教师和学生提供完整的数字化教学体验。
# Django教学平台

## 核心功能

### 教师端功能
- **班级管理**：创建/管理班级，管理班级成员
- **课程管理**：上传Markdown格式的课程文档
- **作业管理**：发布包含多种题型的作业（选择题/判断题/填空题/解答题）
- **学习监控**：查看班级/学生作业完成情况
- **数据可视化**：使用ECharts展示学生成绩和学习进度统计

### 学生端功能
- **作业系统**：查看/完成教师发布的作业
- **自动评分**：提交后系统自动评估客观题并给出分数
- **成绩查询**：查看个人作业成绩和班级排名
- **学习统计**：通过ECharts图表查看个人学习进度

## 技术栈
- **后端框架**：Django 4.x
- **前端技术**：HTML5, CSS3, JavaScript, Bootstrap
- **可视化库**：ECharts
- **数据库**：可替换为MySQL8.0+
- **Markdown支持**：django-markdownx
- **自动评分**：Django自定义评分引擎

## 部署指南

### 前提条件
- Python 3.8+
- pip 最新版

### 一键部署
```bash
# 迁移数据库
python manage.py migrate

# 创建超级用户（教师账号）
python manage.py createsuperuser

# 赋予执行权限
chmod +x run.sh

# 执行部署脚本（部署时需要查看run.sh中的media路径，如果不熟悉建议手动部署）
./run.sh
```

### 手动部署步骤
1. 克隆仓库：
   ```bash
   git clone https://github.com/yourusername/django-learning-platform.git
   cd django-learning-platform
   ```

2. 创建虚拟环境：
   ```bash
   python -m venv venv
   source venv/bin/activate  # Linux/Mac
   venv\Scripts\activate  # Windows
   ```

3. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```

4. 数据库迁移：
   ```bash
   python manage.py migrate
   ```

5. 创建超级用户（管理员）：
   ```bash
   python manage.py createsuperuser
   ```

7. 运行开发服务器：
   ```bash
   python manage.py runserver
   ```

8. 访问系统：
   - `http://localhost:8000/`

## 使用说明

### 教师账户
1. 使用`createsuperuser`创建的账户登录管理员后台
2. 创建班级并添加学生
3. 在"课程"模块上传Markdown格式的教学文档
4. 在"作业"模块创建新作业，设置题目和答案
5. 在"分析"模块查看学生学习情况统计图表

### 学生账户
1. 通过教师提供的班级邀请码注册账户
2. 在"我的课程"查看课程文档
3. 在"我的作业"完成并提交作业
4. 系统自动评分后查看成绩和答案解析
5. 在"学习统计"查看个人学习进度图表

## 自动评分机制
- ✅ **选择题/判断题**：完全匹配标准答案得分
- ✅ **填空题**：支持多个同义答案（使用`|`分隔）
- ✅ **解答题**：需教师手动评分（系统标注待批改状态）
- ⏱ **自动评分流程**：提交后立即执行，实时返回结果

## 贡献指南
欢迎提交Pull Request，请遵循以下步骤：
1. Fork项目仓库
2. 创建特性分支 (`git checkout -b feature/new-feature`)
3. 提交修改 (`git commit -am 'Add new feature'`)
4. 推送分支 (`git push origin feature/new-feature`)
5. 创建Pull Request

## 许可证
[MIT License](LICENSE)

---

> **注意**：实际部署前请确保：
> 1. 在`config/settings/production.py`中设置`SECRET_KEY`
> 2. 配置适合生产环境的数据库
> 3. 设置`DEBUG=False`并配置`ALLOWED_HOSTS`

系统截图请参见项目目录中的`screenshots/`文件夹
