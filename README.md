# Лабораторная работа №1

Воробьева Дарья Сергеевна, группа 221341, вариант 4, лабораторная работа №1.


## Задания

### Средней сложности

- №4: Изменить файл, сделать второй коммит
- №6: Слить ветку `feature` с основной
- №10: Склонировать чужой репозиторий и изучить историю

### Повышенной сложности

- №5: Переписать историю коммитов с `git rebase`
- №9: Сформировать отчёт о коммитах с `git shortlog`


## Доказательство выполнения

### Средняя сложность №4

Создала файл `main.py` и сделала первый коммит. Затем изменила этот файл и снова сделала коммит.

### Средняя сложность №6

Создала новую ветку `feature`:

```bash
git branch feature
git checkout feature
```

Создала в этой ветке новый файл `feature.py` и сделала коммит:

```bash
echo "print('New file')" > feature.py
git add feature.py
git commit -m "feat: создала новую ветку и добавила новый файл"
```

Вернулась в основную ветку `main`:

```bash
git checkout main
```

Слила ветки:

```bash
git merge --no-ff feature
```

Получилось так:

```bash
*   7d7c0e7 (HEAD -> main) feat: Merge branch 'feature'
|\  
| * 765a6a9 (feature) feat: обновленный файл
|/  
* b8aae87 (origin/main) feat: отчёт о коммитах
```

### Средняя сложность №10

Адрес склонированного репозитория: https://github.com/TheAlgorithms/Python.git

Лог сохранён в файле `documentslab/clone.md`.


## Повышенная сложность №5

**Лог до rebase:**

```
git log --oneline
4f626cc (HEAD -> main) feat: коммит второй
4688df8 feat: коммит первый
9456c63 docs: доказательство клонирования
88d250f feat: "Merge branch 'feature'"
917a6f4 (feature) feat: создала новую ветку и добавила новый файл
e0b9aa0 feat: изменила main.py
a9f8199 feat: создала main.py
```

**Лог после rebase:**

```
git log --oneline
d1f0992 (HEAD -> main) feat: объединенный коммит
9456c63 docs: доказательство клонирования
88d250f feat: "Merge branch 'feature'"
917a6f4 (feature) feat: создала новую ветку и добавила новый файл
e0b9aa0 feat: изменила main.py
a9f8199 feat: создала main.py
```


## Повышенная сложность №9

С помощью `git shortlog` сформировала отчёт о коммитах. Смотреть в файле `shortlog.txt`.