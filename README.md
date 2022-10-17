# excalidraw.alswl.com

https://excalidraw.alswl.com

Build:

```
cd excalidraw
docker build .
docker run -it --rm -p 127.0.0.1:8000:80 101ad3eda799 # replace with your image id


# in another terminal

docker ps # get container id

cd excalidraw.alswl.com
docker cp 56edaa0a8f96:/usr/share/nginx/html/ - > files.tgz # replace your container id
tar xzvf files.tgz
mv html/* .
rmdir html
rm files.tgz
```
