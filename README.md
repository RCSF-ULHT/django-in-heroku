# django-in-heroku ⛅

Execute os seguintes comandos para pôr o seu projeto e app a correr na cloud!
1. considera-se que tem o Heroku instalado. Na consola, faça login `heroku login`
2. Instale o servidor gunicorn	`pipenv install gunicorn`
3. Crie na pasta lab6 o ficheiro `Procfile` (sem qualquer extensão!) com o seguinte conteúdo (que especifica que estamos a usar Gunicorn): `web: gunicorn config.wsgi --log-file -`
4. em config/settings.py, pôr: `ALLOWED_HOSTS = ['*']` 
5. fazer push para o github:
	```
	git add -A
	git commit -m "projeto django"
	git push -u origin master
	```
6. criar nova app no Heroku, com nome aleatório com o comando `heroku create`
7. indicamos para ignorar ficheiros estáticos tais como CSS e JS (os quais Heroku tenta otimizar para nós), com o comando: `heroku config:set DISABLE_COLLECTSTATIC=1`
8. fazer push do código para o Heroku `git push heroku master`
9. lançamos a aplicação	`heroku ps:scale web=1`
10. confirmamos se a app esta online `heroku open`
