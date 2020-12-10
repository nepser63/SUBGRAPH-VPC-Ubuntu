Запускаем тестовый SUBGRAPH на VPC Ubuntu 18.04 Digitalocean 
(https://nepserg84.medium.com/%D0%B7%D0%B0%D0%BF%D1%83%D1%81%D0%BA%D0%B0%D0%B5%D0%BC-%D1%82%D0%B5%D1%81%D1%82%D0%BE%D0%B2%D1%8B%D0%B9-subgraph-%D0%BD%D0%B0-vpc-ubuntu-18-04-digitalocean-3bf7525dd9a1)
Создаём VPC в Digitalocean
Итак, первым делом создаём виртуальную машину - "Droplet" в Digitalocean. Выбираем ОС Ubuntu 18.04, пакет за 15$. Чтобы получить бесплатно на 60 дней бонус 100$, регистрируйтесь по реферальной ссылки: referel link%: https://m.do.co/c/8bdaf93a979f
Выбираем любой регион для сервера, задаём свой пароль для входа в ubuntu и указываем имя нашего хоста
Работа с Ubuntu
Для быстрой и удобной работы с Ubuntu рекомендую скачать файловый менеджер win scp, эта программа пригодится для копирования и переноса файлов с сервера на локальный компьютер. Чтобы запустить ubuntu, можете воспользоваться консолью в Digitalocean, но для более удобной работы я установил PuTTY, она отлично работает вместе win scp, скачать её можно здесь.
Итак, после установки программ, запускаем win scp, он вам сразу предложит совместную работу с PuTTY.
Далее как на примере выше запускаем ubuntu, для этого открываем win scp, выбираем new site (новый сайт) указываем ip нашей виртуальной машины (VPC) в host name, вводим пароль (который задали VPC), сохраняем настройки входа и нажимаем login для выхода. У вас должно открыться консоль с ubuntu и в win scp откроется корневая папка ОС.
Создаём тестовый Subgraph
Прежде чем начать установку, заходим на сайт https://thegraph.com/explorer/ и входим(sign up with Github) с помощью учётной записи github, если её нет, то регистрируем её.
После авторизации в верхнем углу вы увидите лого с github, нажмите по нему и выберете Dashboard, вы перейдете в панель инструментов. Далее добавляем наш сабграф - Add Subgraph.
Добавьте или оставьте изображение по умолчанию. Затем введите имя вашего сабграфа (изменить после создания не получится), описание и ссылки ниже можно будет добавить и после создания.
В конце нажимаем создать сабграф"Create subgraph"
Сабграф создан теперь надо его развернуть и синхронизировать.
Далее возвращаемся к нашей консоли с ubuntu и вводим по порядку необходимые команды для установки сабграфа.
Команды для установки сабграфа.
Вводим все команды в консоли Ubuntu по очереди.
ssh @ IP
1. sudo apt update 
 sudo apt upgrade
2. sudo apt install git 
3. git config - global user.name имя_сабграфа
4. git config - global user.email эл.почта (с гитхаба)
5. curl -sL https://deb.nodesource.com/setup_14.x | \sudo -E bash - && \
6. sudo apt install -y nodejs && sudo npm install -g npm@latest
7. wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.8/install.sh | bash
8. source ~/.profile
9. nvm install 14.15.1
10. curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
11. echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
12. sudo apt update
13. sudo apt install yarn
14. yarn global add @graphprotocol/graph-cli
15. graph init - from-example гитхаб_юзер/имя_субграфа
16. yarn install
cd имя_сабграфа
graph deploy - access-token (токен вашего сабграфа, справа от имени сабграфа)\
 - debug \
 - node https://api.thegraph.com/deploy/ \
 - ipfs https://api.thegraph.com/ipfs/ \
 гитхаб_юзер/имя_субграфа
После введения всех команд, перейдите на страницу своего субграфа, чтобы убедиться, что он синхронизировался как в примере ниже.
Для полного завершения создаём репозиторий в своём гитхабе и переносим туда файлы с локального компьютера/сервера, предварительно скопировав их из папки своего сабграфа с помощью файлового менеджера win scp.
Успеха!
