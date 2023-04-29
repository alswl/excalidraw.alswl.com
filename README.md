# excalidraw.alswl.com

https://excalidraw.alswl.com

Docs:

- [Self hosted online collaborative drawing platform Excalidraw | Log4D](https://en.blog.alswl.com/2022/10/self-hosted-excalidraw/)
- [私有化在线协同画图平台 Excalidraw | Log4D]( https://blog.alswl.com/2022/10/self-hosted-excalidraw/ )

Build:

```
# using my forked excalidraw
git clone git@github.com:alswl/excalidraw.git
cd excalidraw
# choose the latest tag from fork or upsteram
git checkout fork
docker build . -t excalidraw-fork
docker run -it --name alswl-excalidraw --rm -p 127.0.0.1:8000:80 excalidraw-fork


# in another terminal

docker ps # check running state

cd excalidraw.alswl.com
rm -rf public
mkdir public
cd public
docker cp alswl-excalidraw:/usr/share/nginx/html/ - > files.tgz # replace your container id
tar xzvf files.tgz
mv html/* .
rmdir html
rm files.tgz
cd ..

# check and save your work
git add .
```

Run:

Local:

```
cd public
python3 -m http.server

# open in another terminal
# open 'http://127.0.0.1:8000/'
```

Prodution: hosting in [Cloudflare Pages](https://pages.cloudflare.com/).

