# excalidraw.alswl.com

https://excalidraw.alswl.com

Docs:

- [Self hosted online collaborative drawing platform Excalidraw | Log4D](https://en.blog.alswl.com/2022/10/self-hosted-excalidraw/)
- [私有化在线协同画图平台 Excalidraw | Log4D]( https://blog.alswl.com/2022/10/self-hosted-excalidraw/ )

Build:

```
cd excalidraw
docker build . -t excalidraw-fork
docker run -it --name alswl-excalidraw --rm -p 127.0.0.1:8000:80 excalidraw-fork


# in another terminal

docker ps # get container id

cd excalidraw.alswl.com
rm -rf public
mkdir public
cd public
docker cp alswl-excalidraw:/usr/share/nginx/html/ - > files.tgz # replace your container id
tar xzvf files.tgz
mv html/* .
rmdir html
rm files.tgz
```
