# ref web: https://blog.gtwang.org/virtualization/docker-basic-tutorial/2/

# base image，這邊採用的是官方的image
# https://hub.docker.com/_/python
FROM python:2.7-slim

# 工作目錄於該container中的root的app dir
WORKDIR /app

# 當前dir中的內容，都放進container的/app內
ADD . /app

# 這邊尚未進入image之中，等於是以當前環境來運作
# 他是疊加的概念，因此他這邊是在有python:2.7-slim的linux下去實踐
# 不然你不可能有辦法執行pip install
RUN pip install -r requirements.txt

# 暴露80 port實際上run的時候才會設置實際的publish
EXPOSE 80

# 產生NAME環境變數，內容為字串world
ENV NAME world

# 這是Container啟動時候會執行的命令 python app.py
# 是以list of strings形式，然後逐個空格這樣產生命令
CMD ["python", "app.py"]
