# 疯狂的joy docker版
## 打包
```bash
## 在根目录下执行
docker build ./docker/jd_crazy --tag qq1398371419/jd_crazy
```
## 运行
```bash
mkdir -p /data/jd_crazy/logs && \
cd /data/jd_crazy && \
docker run -dit \
  -e JD_COOKIE='' \ # jd cookie，用'&'分割
  -e MERGE_WAIT=1800000 \
  -e PRODUCE_WAIT=1000 \
  -v /data/jd_crazy/logs:/scripts/logs \
  --name jd_crazy \
  --hostname jd_crazy \
  --restart always \
  qq1398371419/jd_crazy
```

环境变量
- JD_COOKIE 通用京东cookie，只能以'&'分割
- MERGE_WAIT 多久运行一次购买合并joy，默认1分钟
- PRODUCE_WAIT 多久运行一次模拟挂机，默认1秒



