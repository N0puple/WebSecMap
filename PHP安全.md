# PHP 知识点

## 基础漏洞

- SQL
  - union 注入
  - 报错注入
  - bool盲注
  - 时间盲注
  - 二次注入
  - fullsearch 注入
  - 预编译注入
  - limit 注入
  - order by 注入
  - 拥有足够权限的情况下，直接 into outfile 写入文件

  - 过滤小括号绕过
    - 可以 union 就直接 union

    - 可以 bool ，通过 order by 实现

    - 可以 bool，通过 regexp / like 实现

    - 只能时间盲注，笛卡尔积实现
- XSS
- XXE
  - 通过上传 Word 造成 XXE
  - 盲 XXE
  - XXE 执行命令
  - 
- SSRF
  - 盲 SSRF
  - SSRF
  - gopher
- 代码执行
  - eval
  - assert
- 命令执行
  - system
  - passthru
  - exec
  - shell_escapeargs xxx 绕过
- 反序列化
  - 反序列化逃逸
    - 后面部分逃逸
    - 前面部分逃逸
  - __wakeup 绕过，CVE-2016-7124，通过更改参数个数
  - __wakeup 绕过，通过 引用 R 来实现
  - gmp 反序列化
  - phar 反序列化
  - GC 绕过  exception 限制
  - fast destruct
  - 对象遍历
  - 间接加载目标类
  - 
- 文件上传
  - windows 保存文件会抹去最后的点绕过
  - .htaccess 绕过黑名单
  - .user.ini 绕过黑名单
  - 
- 变量覆盖
  - parse_str
  - extract
  - 
- 目录穿越
- 文件读取/写入
- 模板注入 SSTI
  - Twig 模板注入
  - smarty 模板注入
- 文件包含
  - 本地包含
    - 日志文件包含
    - session 包含（需要开启 session.upload_progress.enable）
    - 通过上传文件产生的临时文件包含（文件名未知，因此需要从 phpinfo 中读取或者是利用windows通配符获取，然后利用条件竞争访问）
    - crash 后导致临时文件驻留从而包含
    - pearcmd 包含（可以bypass限制php后缀，需要存在 pearcmd）
    - 利用伪协议包含（可以bypass限制php后缀）
    - nginx下post 大 body 产生临时文件进行包含
  - 远程包含（默认不开启 allow_url_include）
  - php://filter
  - 使用 phar文件 bypass 后缀限制
- csrf
- crlf
- ldap 注入
- 


## PHP Tricks

- basename 绕过
- parse_url 绕过
- json_encode
- GC 机制 绕过
  - 置空绕过
  - 覆盖绕过
  - unset 绕过

- file_exists / is_file 绕过 windows 才可以绕过
- trim 去除两边的空白字符
- is_numeric
- PCRE 回溯绕过
- open_basedir 绕过
- disabled_function 绕过
- 死亡 exit 绕过
- 



## 框架漏洞

- ThinkPHP
  - ThinkPHP 5.0.24 RCE
  - ThinkPHP 5.1.41 文件上传 getshell CVE-2022-44289
  - ThinkPHP 6.0.13 文件包含 RCE
  
- Laravel
  - Laravel Debug RCE

- Zendframework
- Laminas
- Yii
- Yii2
- Drupal
- Codeigniter
  - Codeigniter3 SQL注入

- 























