# γ

## Setup

```sh
sudo apt install ansible docker-ce
ansible-playbook setup.yml
docker context create --docker=host=ssh://ubuntu@beta.fogtype.com beta
docker context create --docker=host=ssh://ubuntu@gamma.fogtype.com gamma
```

詳しい構成は [setup.yml](setup.yml) を参照
