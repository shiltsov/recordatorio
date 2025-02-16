## tmux - terminal multiplexer

Инструмент, позволяющий создавать несколько окон и панелей в одной сессии терминала, переключаться между ними, сохранять их состояние и восстанавливать после разрыва соединения.
**Устанавливается на сервере**

`$ sudo apt install tmux`

### как пользоваться

Заходим на сервер по ssh, далее либо создаем новый tmux сеанс либо подключаемся к существующему (восстанавливается состояние)

```
$ tmux ls  - список активных сеансов
$ tmux attach  - подключиться к сеансу (последнему)

(внутри сессии tmux)
$ exit - выход из сессии tmux

$ tmux new -s sda00  - новая сессия, выйти сохранив ее рабочей Ctrl-b d
$ tmux attach -t sda00 - подключиться к уже существующей сессии по имени

```

**Ctrl-b d** - детач сессии (отключение без завершения)<br>
**Ctrl-b c** - создать новое окно<br>
**Ctrl-b x** - закрыть текущую панель<br>
**Ctrl-b n , Ctrl-b p** - следующая - предыдущая панели<br>

в общем идея в том что на сервере запускаем все под tmux а при разрыве соединения подключаемся и подключаемся к сессии tmux (которая не перестает работать при разрыве)

### разбиение на подокна

**Cnrl-b %** - добавить панель справа от текущей  <br>
**Cnrl-b "** - добавить панель снизу от текущей  <br>
**Cnrl-b [стрелки]** - переключение между панелями<br>
**Cnrl-b(удерживать) [стрелки]** - изменить размеры панелей <br>
**Cnrl-b { и }** - перемещать / менять местами порядок панелей<br>

![1](https://github.com/user-attachments/assets/d7bc7404-b4d3-4f7d-99b8-7fdc9e18b47a)
