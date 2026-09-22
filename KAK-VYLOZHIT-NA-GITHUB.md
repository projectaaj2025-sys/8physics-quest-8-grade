# 📤 Как выложить игру на GitHub — пошагово

## Способ 1. Через сайт (самый простой, без программ)

1. Зайдите на **[github.com](https://github.com)** и войдите в свой аккаунт
   (если аккаунта нет — кнопка **Sign up**, займет 2 минуты).
2. Нажмите **`+`** справа вверху → **New repository**.
3. Заполните:
   - **Repository name:** `physics-quest`
   - **Description:** Физика-Квест — игра по физике 8 класса
   - Выберите **Public** (нужно для бесплатного GitHub Pages)
   - Галочку «Add a README» можно не ставить — README уже в папке
4. Нажмите **Create repository**.
5. На открывшейся странице нажмите ссылку **uploading an existing file**
   (или кнопку **Add file → Upload files**).
6. **Перетащите мышкой все файлы** из папки `physics-quest-github`
   (index.html, screenshot.png, README.md, КАК-ВЫЛОЖИТЬ-НА-GITHUB.md, .gitignore и папку uploads).
   > ⚠️ Файл `.gitignore` начинается с точки — в некоторых проводниках он скрыт.
   > Включите показ скрытых файлов или просто перетащите всю папку целиком.
7. Внизу нажмите зелёную кнопку **Commit changes**. Готово — файлы на GitHub! 🎉

## Способ 2. Через Git (из командной строки)

В папке `physics-quest-github` выполните (подставив свой ник):

```bash
git init
git add .
git commit -m "Физика-Квест: игра с управлением пальцем на телефоне"
git branch -M main
git remote add origin https://github.com/ВАШ_НИК/physics-quest.git
git push -u origin main
```

GitHub попросит логин/пароль — в качестве пароля используйте
**Personal Access Token** (создаётся в GitHub → Settings → Developer settings →
Personal access tokens → Tokens (classic) → Generate new token, отметьте галочку `repo`).

> Перед `git init` не забудьте создать пустой репозиторий на сайте
> (шаги 1–4 выше) и **не** добавляйте README через сайт.

## 🌐 Включаем сайт (GitHub Pages)

1. В вашем репозитории откройте **Settings** (шестерёнка вверху).
2. Слева выберите раздел **Pages**.
3. В блоке **Build and deployment**:
   - **Source:** `Deploy from a branch`
   - **Branch:** `main` и папка `/ (root)` → **Save**
4. Подождите 1–2 минуты и обновите страницу — сверху появится ссылка вида:

   ```
   https://ваш-ник.github.io/physics-quest/
   ```

5. Откройте ссылку **на телефоне** → добавьте в закладки или «На главный экран».
   Игра запускается прямо в браузере, без установки. 🚀

## ❓ Частые вопросы

**Игра не открывается по ссылке / белый экран.**
Проверьте, что файл называется именно `index.html` (маленькими буквами) и лежит в корне репозитория, а в Settings → Pages выбран branch `main`.

**Кнопка «Скачать конспект» не работает.**
В репозитории нет PDF-файлов. Положите их в папку `uploads/` (имена файлов — в `uploads/README.md`) и сделайте новый Commit.

**Можно ли сделать репозиторий приватным?**
GitHub Pages для приватных репозиториев требует платный аккаунт. Для школы/уроков достаточно публичного.

**Как обновить игру?**
Способом 1: Add file → Upload files → перетащить новый `index.html` → Commit changes.
Способом 2: заменить файл локально и выполнить `git add . && git commit -m "Обновление" && git push`.
