# γ

[git.fogtype.com](https://git.fogtype.com/) 用 Drone Server & Runner

## Setup

```sh
sudo apt install ansible docker-ce
ansible-playbook setup.yml
```

詳しい構成は [setup.yml](setup.yml) を参照

## Drone Server & Runner

Gitea への導入
: https://docs.drone.io/server/provider/gitea/

| 項目             | 値                              |
| ---------------- | ------------------------------- |
| Application Name | gamma                           |
| Redirect URI     | https://gamma.fogtype.com/login |

```bash
install -m 600 .env{.example,}
echo DRONE_RPC_SECRET=$(openssl rand -hex 16) >> .env
# .envファイルに適切な設定をする
```

### Deploy

```bash
docker context create --docker=host=ssh://ubuntu@gamma.fogtype.com gamma
docker context use gamma
docker compose up -d
```
