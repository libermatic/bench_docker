# bench_docker

Containerized bench

> WARNING: does not contain redis and mariadb setup

Intended just to run `bench` commands on already existing setups. So maybe
create an alias to ease things up a bit.

```sh
alias bench='docker run --rm -v $HOME/frappe-bench:/home/frappe/frappe-bench libermatic/bench_docker'
```

But if `bench init` is necessary, run

```sh
docker run \
  --rm \
  -v $(pwd)/frappe-bench:/home/frappe/frappe-bench \
  libermatic/bench_docker init \
    --ignore-exist \
    --skip-redis-config-generation \
    frappe-bench
```
