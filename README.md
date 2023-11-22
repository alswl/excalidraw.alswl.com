# excalidraw.alswl.com

Online(no collaboration): https://excalidraw.alswl.com

Feature:

- Chinese font with handwriting style
- Pure static

If you want own your self-host excalidraw, please check my another project: [alswl/excalidraw-collaboration](https://github.com/alswl/excalidraw-collaboration).

Docs related:

- [Self hosted online collaborative drawing platform Excalidraw | Log4D](https://en.blog.alswl.com/2022/10/self-hosted-excalidraw/)
- [私有化在线协同画图平台 Excalidraw | Log4D]( https://blog.alswl.com/2022/10/self-hosted-excalidraw/ )

Build:

```
# using my forked excalidraw
docker run -it --rm --name excalidraw docker.io/alswl/excalidraw:v0.16.1-fork-b1

# open another terminal
docker ps # check running state

cd excalidraw.alswl.com
rm -rf public
mkdir public
cd public
docker cp excalidraw:/usr/share/nginx/html/ - > files.tgz # replace your container id
tar xzvf files.tgz
mv html/* .
rmdir html
rm files.tgz
cd ..

# check and save your work
git add .
```

Run local:

```
cd public
python3 -m http.server

# open in another terminal
# open 'http://127.0.0.1:8000/'
```

Prodution: hosting in [Cloudflare Pages](https://pages.cloudflare.com/).

