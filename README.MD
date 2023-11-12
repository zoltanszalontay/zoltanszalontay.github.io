# Truepositive.eu blog

This blog is based on the code that's behind [https://takacsmark.com](https://takacsmark.com).

This is the GitHub Pages repo of Truepositive.eu's blog on [https://truepositive.eu](https://truepositive.eu).

The blog shows the experiences and results we got during our projects.

## Key features

This is a regular GitHub Pages blog with a few notable features added that you may find useful:

- the blog is served with Docker during development
- development tools based on Gulp are also Dockerized

## Usage

To start the blog in development mode issue the following command:

```terminal
docker-compose up -d
```

This will start up a Jekyll server, it will build the site and serve it on [http://localhost:4000](http://localhost:4000).

To follow the logs use the following command:
```terminal
docker-compose logs -f
```

## Gulp dev tools

Gulp development tools are used to minimize images that I add to the blog. Use the following command to start the development tools:

```terminal
docker-compose -f docker-compose.devtools.yml run gulp
```

This command will give you an interactive shell inside a `node` container that has Gulp pre-installed.

In the terminal, run the following command to generate images located in ./assets/_raw_images/ to different sizes. 
(Please note that the sequence in img:add does not work.)

```terminal
gulp img:minimize
gulp img:generatesizes
```

See the Compose file, `docker-compose.devtools.yml` and `gulpfile.js` for further details.
