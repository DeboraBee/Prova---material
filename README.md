# Prova---material
No Bash (pythonanywhere):

Use workon vEnv (ou venv) antes de fazer as próximas instruções

Se precisar baixar bibliotecas:
pip install flask
pip install flask-bootstrap
pip install flask-mail
pip install flask-moment
pip install flask-wtf
pip install requests
pip install flask-migrate
pip install flask-sqlalchemy
pip install email_validator
pip install flask-login

Comandos para banco de dados no bash:
export FLASK_APP=flasky.py
flask shell
from flasky import db
db.create_all()
db.drop_all()
db.create_all()
from flasky import Role, User
adm_role = Role(name=’Administrator’)
user_role = Role(name=’User’)
db.session.add_all([adm_role, user_role])
db.session.commit()

(crtl + D para sair do flask shell)

Se precisar inserir usuários no banco de dados pelo bash:
flask shell
from flasky import Role, User
adm_role = Role.query.filter_by(name=’Administrator’).first()
user_role = Role.query.filter_by(name=’User’).first()
usuarioAdministrador = User(username=’Susana’, role=adm_role)
usuarioUsuario = User(username=’Mariana’, role=user_role)

Para pegar os arquivos do github e depois conectar no seu novo repositório:
chmod 777 change_repo.sh
./change_repo.sh linkdorepositorio.git
git init
git remote set-url origin linkdomeurepositorio.git

(retire todas as informações do .env antes de continuar!!!)

git add .
git commit -m “arquivos”
git push -u origin master
(vai precisar do nick do github e token)

Para trazer as alterações feitas no repositório do github pro pythonanywhere:
git pull 
(se não funcionar: git pull origin master)

Se quiser substituir tudo que tiver localmente pelo que está no github:
git reset –hard origin/master
(são dois traços antes de hard!)
