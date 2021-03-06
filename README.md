# ESD(Enumeration Sub Domain)
[![asciicast](https://asciinema.org/a/15WhUe40eEhSbwAXZdf2RQdq9.png)](https://asciinema.org/a/15WhUe40eEhSbwAXZdf2RQdq9)

## 优势
#### AsyncIO协程，更快的速度
基于AsyncIO+AioDNS将比传统多进程/多线程/gevent模式快一半以上。
通过扫描`qq.com`，共`170083`条规则，找到`1913`个域名，耗时`163`秒左右，平均`1000+条/秒`。

#### 融合字典，更全的结果
> 去重后共170083条子域名字典

- 通用字典
    - 单字母
    - 单字母+单数字
    - 双字母
    - 双字母+单数字
    - 双字母+双数字
    - 三字母
    - 单数字
    - 双数字
    - 三数字
- 域名解析商公布使用最多的子域名
    - DNSPod: dnspod-top2000-sub-domains.txt
- 其它域名爆破工具字典
    - subbrute: names_small.txt
    - subDomainsBrute: subnames_full.txt

## 使用
仅在Python3下验证过
```
# 安装依赖
pip install -r requirements.txt

# 扫描单个域名
python ESD.py qq.com

# 扫描多个域名（英文逗号分隔）
python ESD.py qq.com,tencent.com

# 扫描文件（文件中每行一个域名）
python ESD.py targets.txt
```

## 后续
- 增加本地DNS缓存，提升重复域名查询的效率
- 支持泛解析域名
- 支持三级、四级子域名

## 参考
- https://github.com/aboul3la/Sublist3r
- https://github.com/TheRook/subbrute
- https://github.com/lijiejie/subDomainsBrute
