# no.nimos.ws

Static one-pager — "No Nimos Allowed" joke page with a single image.

- kind: `static` (served by host nginx; see nginx.conf). Repo is **public**.
- OG meta tags included (title, image, description).

## Notable

- Image (`nonimos.jpg`) is served from root-relative `/nonimos.jpg` — correct for nginx static serve.
- No external dependencies; fully self-contained.
- No build step; deploy as-is.

## Local test

    docker run --rm -d -p 8090:80 -v "$PWD:/usr/share/nginx/html:ro" --name nonimos-test nginx:alpine
    curl -s localhost:8090 | head            # then: docker rm -f nonimos-test
