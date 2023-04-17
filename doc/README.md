```shell
cd docker
sudo docker-compose build auto-gpt
sudo docker tag docker_auto-gpt yiluxiangbei/auto-gpt
sudo docker push yiluxiangbei/auto-gpt

sudo docker-compose run --rm auto-gpt --gpt3only --continuous

sudo docker build -t autogpt .
sudo docker run -it --env-file=./.env -v $PWD/auto_gpt_workspace:/app/auto_gpt_workspace autogpt
sudo docker-compose run --build --rm auto-gpt

sudo docker run -it --env-file=./.env -v $PWD/auto_gpt_workspace:/app/auto_gpt_workspace autogpt --gpt3only --continuous
sudo docker-compose run --build --rm auto-gpt --gpt3only --continuous

docker rmi `docker images|grep none |  awk '{print $3}'`
```

```
公众号 聊天
```