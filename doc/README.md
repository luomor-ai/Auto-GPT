```shell
sudo docker build -t autogpt .
sudo docker run -it --env-file=./.env -v $PWD/auto_gpt_workspace:/app/auto_gpt_workspace autogpt
sudo docker-compose run --build --rm auto-gpt

sudo docker run -it --env-file=./.env -v $PWD/auto_gpt_workspace:/app/auto_gpt_workspace autogpt --gpt3only --continuous
sudo docker-compose run --build --rm auto-gpt --gpt3only --continuous
```