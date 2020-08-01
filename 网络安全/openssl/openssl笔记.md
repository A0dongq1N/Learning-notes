# openssl

## 利用openssl生成自签名证书

1. 检查openssl版本

   ```shell
   openssl version
   ```

   

2. 生成私钥

   ```shell
   # genrsa 生成RSA 私钥
   # -des3 des3算法
   # -out server.key 生成的私钥文件名
   # 2048 私钥长度
   openssl genrsa -des3 -out server.pass.key 2048
   # 运行完之后需要输入一个4位密码
   ```

   

3. 去掉私钥中的密码

   ```shell
   openssl rsa -in server.pass.key -out server.key
   ```

   

4. 生成CSR

   ```shell
   # req 生成证书签名请求
   # -new 新生成
   # -key 私钥文件
   # -out 生成的CSR文件
   # -subj 生成CSR证书的参数
   openssl req -new -key server.key -out server.csr -subj "/C=CN/ST=Guangdong/L=Guangzhou/O=xdevops/OU=xdevops/CN=gitlab.xdevops.cn"
   # /C= 国家
   # /ST= 省
   # /L= 城市
   # /O= 组织
   # /OU=  部门
   # /CN= 域名或IP
   ```

   

5. 生成自签名SSL证书

   ```shell
   # -days 证书有效期
   openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt
   ```

   