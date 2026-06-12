# 1. Создание SSH ключа
Для начал нужно создать и сгенировать ключь shh, для подключения по нему.
Команды для PowerShell WIndows
```
mkdir .ssh
cd .ssh
dir
```
Генерируем ключ
```
ssh-keygen -t rsa -b 4096 -C "ваш_email@example.com"
```
При генерации ключа, мы можем выбрать где его сохранить и просить добавить пароль (не обязательно)
Если мы добавили пароль нужно использовать следующие команды:
```
Get-Service ssh-agent | Set-Service -StartupType Automatic
Start-Service 
ssh-agentssh-add $env:USERPROFILE\.ssh\id_rsa
```

Чтобы посмотреть получившийся ключ используем:
```
Get-Content -Path "$env:USERPROFILE\.ssh\id_rsa.pub"
```

