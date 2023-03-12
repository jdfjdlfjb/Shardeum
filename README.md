# Встановлення ноди Shardeum

## Рекомендовані вимоги до сервера
-60 GB ssd storage

-Quad core CPU less than 10 years old if self hosting

-Dual core CPU works if hosted with newer Xeons / EPYC

-16 GB of ram,  4+ GB of virtual memory recommended

-Hosting: 8 GB RAM + 8 GB Virtual Memory


### Оновлюємо наш сервер
```
sudo apt update && sudo apt upgrade -y
```

### Встановлюємо додаткові пакети
```
sudo apt install make clang git pkg-config libssl-dev build-essential git gcc chrony curl jq ncdu bsdmainutils htop net-tools lsof fail2ban wget -y
```

### Встановлюємо docker
```
sudo apt install docker.io
```

### І docker-compose
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

### Надаємо права docker-compose
```
sudo chmod +x /usr/local/bin/docker-compose
```

### Завантажуємо інсталяційні пакети проекту і запускаємо встановлення
```
curl -O https://gitlab.com/shardeum/validator/dashboard/-/raw/main/installer.sh && chmod +x installer.sh && ./installer.sh
```

### Погоджуємося зі встановленням дашборда (говоримо y)
```
Do you want to run the web based Dashboard? (y/n): y 
```

### Задаємо пароль для дашборда
```
Set the password to access the Dashboard: 
```

### Вводим порт для доступа к дашборду (по умолчанию 8080)
```
Enter the port (1025-65536) to access the web based Dashboard (default 8080): 
```

### Вводимо порти p2p (за замовчуванням 9001 і 10001)
```
This allows p2p communication between nodes. Enter the first port (1025-65536) for p2p communication (default 9001):
Enter the second port (1025-65536) for p2p communication (default 10001):
```

### Задаємо папку для встановлення (за замовчуванням ~/.shardeum)
```
What base directory should the node use (defaults to ~/.shardeum): 
```

### Запускаємо встановлення CLI
```
cd ~/.shardeum
./shell.sh
```

### Запускаємо CLI
```
operator-cli gui start
```

### Переходимо у веб інтерфейс (відповідно якщо змінювали порт то вказуємо його)
```
https://your_node_ip:8080/
```

 Оскільки немає сертифіката, видасть помилку (для інших браузерів трохи інакше, але суть одна)
![6](https://user-images.githubusercontent.com/112564909/224557563-96a65f39-aea7-40cb-8677-ca3c64ab311d.jpg)

## Вибираємо додатково (advanced) і тиснемо перейти за адресою
## Після цього потрібно ввести пароль, який задавали для доступу до дашборду
## Якщо забули пароль, то з терміналу введіть команду зміни пароля
```
operator-cli gui set password <type_new_password__here>
```

 Потрапляємо на вкладку Overview де можна побачити інформацію про ноду, далі потрібно перейти на вкладку Maintenance
![7](https://user-images.githubusercontent.com/112564909/224557682-b9e8f41b-9a52-4c94-9bb7-008f12843593.jpg)

 На цій вкладці у верхньому лівому блоці запускаємо ноду натиснувши на "Start Node" (якщо нічого не змінилося перезавантажте сторінку)

![8](https://user-images.githubusercontent.com/112564909/224557751-0b70f2ea-6a37-497c-8e71-23ac519df457.jpg)

### Так само можна запустити через термінал такою командою
```
operator-cli start
```

### Відповідно для зупинки ноди натискаємо в дашборді "Stop Node" або через термінал виконуємо команду
```
operator-cli stop
```

 Тепер необхідно запросити кошти на метамаск, для початку переходимо за посиланням і підключаємо мережу Sphinx 1.X

 Далі переходимо за посиланням натискаємо https://discord.com/invite/shardeum

![9](https://user-images.githubusercontent.com/112564909/224557924-9c442dd3-8a5e-4d8d-b6e8-c8b4f5f937ed.jpg)

 Вводимо команду /faucet <адреса метамаска> і запитуємо кошти
 Після того як кошти надійшли повертаємося в дашборд і в правому верхньому блоці натискаємо "connect wallet"

![10](https://user-images.githubusercontent.com/112564909/224558004-0388467c-f40b-4182-895b-c62a7209ecb6.jpg)


 Після підключення натискаємо "Add Stake" вводимо суму (мінімальна рекомендована 10 токенів) і тиснемо "Stake"

![11](https://user-images.githubusercontent.com/112564909/224558054-0d591923-7603-4b28-96e6-b4cb5a324994.jpg)

