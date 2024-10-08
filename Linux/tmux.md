Tmux (ти-макс) — это **менеджер терминалов**, который позволяет работать с несколькими сессиями в одном окне. То есть вместо нескольких открытых окон терминала — вы используете одно, которое можно делить на несколько окон.

Киллер фича ти-макса — сохранение состояний подключений и процессов. После разрыва соединения с сервером вы подключаетесь, и все запущенные программы и процессы продолжают работать.

Несколько основных команд tmux для управления сессиями:

- **attach-session (attach)** - подключиться к уже существующей сессии. В параметре необходимо передать опцию -t и идентификатор сессии;
- **detach-session (detach)** - отключить всех клиентов (или переданного с помощью опции -t) от сессии, переданной в опции -s;
- **has-session** - проверить существует ли сессия, аналогично, надо передать идентификатор сессии;
- **kill-server** - остановить все запущенные сессии;
- **kill-session** - завершить сессию переданную в параметре -t;
- **list-clients** - посмотреть клиентов, подключенных к сессии -t;
- **list-sessions (ls)** - вывести список всех запущенных сессий;
- **new-session** - создать новую сессию, можно передать имя сессии в опции -s и стартовую директорию в опции -c;
- **rename-session** - переименовать сессию, нужно передать идентификатор сессии и новое имя;

По умолчанию для активации сочетания клавиш нужно нажать Ctrl+B, отпустить, а потом нажать нужную клавишу. Вот основные сочетания клавиш tmux, которые вам понадобятся:

- **Ctrl+b c** - создать новое окно;
- **Ctrl+b w** - выбрать окно из списка;
- **Ctrl+b 0-9** - открыть окно по его номеру;
- **Ctrl+b ,** - переименовать текущее окно;
- **Ctrl+b %** - разделить текущую панель по горизонтали;
- **Ctrl+b "** - разделить текущую панель по вертикали;
- **Ctrl+b стрелка** - перейти на панель, находящуюся в стороне, куда указывает стрелка;
- **Ctrl+b Ctrl+стрелка** - изменить размер текущей панели;
- **Ctrl+b o** - перейти на следующую панель;
- **Ctrl+b ;** - переключаться между текущей и предыдущей панелью;
- **Ctrl+b x** - закрыть текущую панель;
- **Ctrl+b [** - войти в режим копирования (подробнее ниже);
- **Ctrl+b ]** - вставить из внутреннего буфера обмена tmux;
- **Ctrl+b d** - отключится от текущей сессии;
- **Ctrl+b :** - открыть командную строку.

С версии 2.1 для включения режима мыши (скролл, изменение размера панели, выбор панели и др.) нужно добавить в tmux.conf:  
  
```
set -g mouse on
```

**Список поддерживаемых комманд**  
``` bash
tmux list-commands
```  
  
**Дополнительная информация**  
``` bash
man tmux
```

---

`tmux` (Terminal Multiplexer) — это мощный инструмент для работы в терминале, который позволяет управлять несколькими окнами и панелями в одном терминальном сеансе. Вот основные команды и функции `tmux`:

### Основные команды tmux:

- `tmux` — запускает новую сессию `tmux`.
- `tmux new -s <session-name>` — создаёт новую сессию с заданным именем.
- `tmux attach -t <session-name>` — подключается к существующей сессии с заданным именем.
- `tmux ls` — выводит список всех запущенных сессий.
- `tmux kill-session -t <session-name>` — завершает указанную сессию.
- `tmux kill-server` — завершает все сессии и выключает `tmux`.

### Управление сессией:

- `Ctrl+b`, `d` — отсоединиться от текущей сессии, оставаясь в фоне (detach).

### Управление окнами:

- `Ctrl+b`, `c` — создать новое окно.
- `Ctrl+b`, `&` — закрыть текущее окно.
- `Ctrl+b`, `,` — переименовать текущее окно.
- `Ctrl+b`, `p` — перейти к предыдущему окну.
- `Ctrl+b`, `n` — перейти к следующему окну.
- `Ctrl+b`, `<number>` — перейти к окну по его номеру.

### Управление панелями:

- `Ctrl+b`, `"` — разделить текущее окно горизонтально.
- `Ctrl+b`, `%` — разделить текущее окно вертикально.
- `Ctrl+b`, `x` — закрыть текущую панель.
- `Ctrl+b`, `o` — переключиться на следующую панель.
- `Ctrl+b`, `;` — перейти к последней активной панели.

### Режим копирования:

- `Ctrl+b`, `[` — войти в режим копирования.
    - Навигация с помощью клавиш `h`, `j`, `k`, `l` (vi-style) или стрелок.
    - `Space` — начать выделение текста.
    - `Enter` — скопировать выделенный текст.
- `Ctrl+b`, `]` — вставить скопированный текст.

### Перемещение и изменение размеров панелей:

- `Ctrl+b`, стрелки — перемещение между панелями.
- `Ctrl+b`, `Ctrl+стрелка` — изменение размеров панелей.

### Дополнительные команды:

- `tmux save-buffer -b <buffer-name> <file>` — сохранить буфер в файл.
- `tmux load-buffer -b <buffer-name> <file>` — загрузить буфер из файла.
- `tmux list-buffers` — выводит список всех буферов.
- `tmux show-messages` — выводит сообщения сервера `tmux`.

Это базовый набор команд, но `tmux` обладает гораздо большими возможностями, включая настройку конфигурационных файлов (`~/.tmux.conf`) и скриптов.