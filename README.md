# Nodebook

This image is a Jupyter notebook build with NodeJS (via Babel) and
CoffeeScript kernels added via https://github.com/n-riesco/jp-babel
and https://github.com/n-riesco/jp-coffeescript respectively.

## Usage

- Port 8888 is used to communicate with the notebook server so include
`-p 8888:8888` so you can access the server.
- `/opt/notebooks` is where your notebook will be run from, so if you
wish to retain it add a volume pointing there:
`-v my/notebook/directory:/opt/notebooks
- `/node_modules` is where any node packages needed will live, so if you
wish to add those add a volume pointing there:
`-v my/node_modules:/node_modules`

Example usage:
```
docker run \
  -p 8888:8888 \
  -v $(pwd)/node_modules:/node_modules \
  -v $(pwd)/notebooks:/opt/notebooks \
  --rm -it evilscott/nodebook
```
