FROM 287439122014.dkr.ecr.cn-north-1.amazonaws.com.cn/public:python-3.10
COPY --from=287439122014.dkr.ecr.cn-north-1.amazonaws.com.cn/public:lambda-adapter-0.6.4  /lambda-adapter /opt/extensions/lambda-adapter

ENV PORT=8081
WORKDIR /var/task
COPY requirements.txt ./
RUN python -m pip install -r requirements.txt
COPY *.py ./
ENTRYPOINT exec uvicorn --port=$PORT main:app
