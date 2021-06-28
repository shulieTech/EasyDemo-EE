### 准备工作

Takin 控制台--> Easydemo-gateway--> Easydemo-usercenter-> MySQL（真实表、影子表）

CURL --> Easydemo-gateway--> Easydemo-usercenter-> MySQL（真实表、影子表）


### 登录体验机器
（工作人员会单独发帐号密码）

### 应用目录
    cd /home/takin/easydemo  

#### 执行业务流量到真实表(t_user)    
`
echo 1 | sh curl.sh

{"code":200,"data":"统计业务表数据: 0","error":null}
{"code":200,"data":"统计影子表数据: 0","error":null}
开始发起流量......
流量发完，统计结果
{"code":200,"data":"统计业务表数据: 2","error":null}
{"code":200,"data":"统计影子表数据: 0","error":null}

` 

### 执行压测流量到影子表(pt_t_user)
` echo 2 | sh curl.sh

{"code":200,"data":"统计业务表数据: 2","error":null}
{"code":200,"data":"统计影子表数据: 0","error":null}
开始发起流量......
流量发完，统计结果
{"code":200,"data":"统计业务表数据: 2","error":null}
{"code":200,"data":"统计影子表数据: 3","error":null}
 
`

#### 登录生产压测控制台 Takin
http://demo.forcecop.shulie.io/  

用户名 easydemo 密码easydemo

