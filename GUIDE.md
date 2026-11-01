# Шпаргалка по ЛПР 6

## ДИКТАТОР (ты)
1. На github.com → New → имя `comics-heroes` → Public → Create repository (без README!).
2. Распакуй zip и открой папку в VS Code. Репозиторий УЖЕ инициализирован: есть коммиты и ветки. Осталось подключить GitHub:
```
git remote add origin https://github.com/ТВОЙ_НИК/comics-heroes.git
git push -u origin master
git push origin my-feature-branch
```
Проверка: `git log --oneline --all --graph`
3. Скажи двум участникам ссылку на репозиторий — теперь они делают Fork.
4. Позже: вкладка Pull requests → открыть каждый → Merge pull request.

## УЧАСТНИК (2 человека)
1. Открой ссылку на репозиторий диктатора → кнопка **Fork**.
2. Клонируй СВОЙ форк:
```
git clone https://github.com/ВАШ_НИК/comics-heroes.git
cd comics-heroes
git remote add upstream https://github.com/НИК_ДИКТАТОРА/comics-heroes.git
git checkout -b my-feature-branch
```
3. Скопируй `heroes/TEMPLATE-favorite-hero.html` в `heroes/Фамилия-favorite-hero.html`, заполни.
4. В `index.html` под комментарием добавь строку:
   `<li><a href="heroes/Фамилия-favorite-hero.html">Имя героя</a></li>`
   (у обоих участников строка встанет в одно место — получится конфликт для Шага 3).
5. Коммит и отправка:
```

git commit -m "Добавлена страница с описанием любимого героя комиксов"
git push origin my-feature-branch
```
6. На GitHub в своём форке → **Compare & pull request** → описание → Create pull request.

## Конфликты (Шаг 3)
```
git fetch upstream
git checkout master
git merge upstream/master
git checkout my-feature-branch
git merge master
```
Открой файл с конфликтом в VS Code, выбери нужное (Accept Both Changes), затем:
```
git add index.html
git commit -m "Разрешены конфликты"
git push origin my-feature-branch
```
