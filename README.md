git version

*

Работа с файлом настройки .gitconfig

$ git config --global user.name "User Namovich" 
# имя или ник нужно написать латиницей и в кавычках
$ git config --global user.email username@yandex.ru
# здесь нужно указать свой настоящий email 

$ cat ~/.gitconfig 
$ git config --list

*

$ cd ~/dev/first-project # перешли в нужную папку
$ git init # создали репозиторий 

$ cd <папка с репозиторием> # перешли в папку
$ rm -rf .git # удалили подпапку .git
f - force — заставить

git status

*

Подготовить файлы к сохранению — git add

$ git add --all # подготовили к сохранению все файлы в репозитории
ИЛИ по одному
$ git add todo.txt
$ git add readme.txt
ИЛИ
$ git add . # добавить всю текущую папку

$ git status

*

Выполнить коммит — git commit -m "Сообщеньице тут!"
Просмотреть историю коммитов — git log

*

$ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
ИЛИ $ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"

# скопировать содержимое ключа в буфер обмена:
$ clip < ~/.ssh/id_rsa.pub
# для ed25519:
$ clip < ~/.ssh/id_ed25519.pub
ИЛИ просто через cat (как на курсе)

Проверьте правильность ключа с помощью следующей команды.
$ ssh -T git@github.com
https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints

*

Привязать удалённый репозиторий к локальному — git remote add
$ cd ~/dev/first-project
$ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git
origin (англ. «источник») — стандартный псевдоним, с помощью которого можно обращаться к главному удалённому репозиторию (обычно такой репозиторий один). Это значительно упрощает работу.

Убедиться, что репозитории связаны, — git remote -v
Флаг -v — короткая форма флага --verbose (англ. «подробный»)

*

Отправить изменения на удалённый репозиторий — git push
$ git push -u origin main
В первый раз эту команду нужно вызвать с флагом -u и параметрами origin (имя удалённого репозитория) и main или master (название текущей ветки). Флаг -u свяжет локальную ветку с одноимённой удалённой. Как вы связывали локальный и удалённый репозитории в предыдущем уроке, так же и здесь нужно дополнительно связать ветки.
Далее писать просто - git push