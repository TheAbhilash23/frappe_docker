# Step Guide for initializing project
```
1. git clone https://github.com/TheAbhilash23/frappe_docker
2. cd frappe_docker
3. cp -R devcontainer-example .devcontainer
4. cp -R development/vscode-example development/.vscode 
```
## Compose Docker containers
```
1. docker compose -f devcontainer-example/docker-compose.yml up -d
2. docker exec -e "TERM=xterm-256color" -it devcontainer-example-frappe-1 bash
```
## Inside Docker container (frappe)
```
1. export PATH="${NVM_DIR}/versions/node/v${NODE_VERSION_DEVELOP}/bin/:${PATH}"
2. bench init --skip-redis-config-generation frappe-bench
3. bench new-site --no-mariadb-socket lms.localhost
4. bench --site lms.localhost set-config developer_mode 1
5. bench --site lms.localhost clear-cache
6. bench --site lms.localhost install-app lms
7. bench use lms.localhost
```
