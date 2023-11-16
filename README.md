Quick Agenda

The slides that drive this talk are [here](https://docs.google.com/presentation/d/1ITMRMebvr1AXNFYAm5jg0IlN9m_WWbVfU-3KrGI9wMk/edit#slide=id.p)

At slide 8, we proceed to walk through the following. Using the files in this directory as "cheat sheets" and this README as an order of operations, we just keep changing the single `Containerfile` to demonstrate each piece.
* executable container
    * podman build -t cowsay-app -f Containerfile-cowsay
    * podman run cowsay-app hi!
* web server
    * podman build -t httpd-app -f Containerfile-apache
    * struggle with entrypoint
* add file
    * podman build -t httpd-added -f Containerfile-add-file
    * podman run -d httpd-added
    * open http://localhost
    * whoops
    * podman run -d -p 8080:80 httpd-added
* mount file/directory
    * podman build -t httpd-mount -f Containerfile-mount-file
    * podman run -d -p 8080:80 httpd-mount
    * launch
    * edit file
    * show change
* are containerfiles imperative or declarative?
* back to slides
* after slide 15, we treat the `docker-compose.yml` the same way as the `Containerfile` and walk through each step using the other files here as "cheat sheets"
* one container but in a compose file
    * podman-compose -f docker-compose-one-container.yml up -d
* let's get 2 containers
    * no example yet