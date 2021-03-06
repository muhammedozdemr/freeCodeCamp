# Як відкрити запит на злиття (PR)

Запит на злиття дозволяє вам надсилати зміни з вашого форку на GitHub для безкоштовного CodeCamp.org. Як тільки ви зробите внесення змін до коду або коду задач, вам слід дотримуватися цих рекомендацій, щоб відправити PR.

## Підготувати хороший PR заголовок

Ми рекомендуємо використовувати [звичайний заголовок і повідомлення](https://www.conventionalcommits.org/) для комітів і запросу на злиття. Умовність має такий формат:

> `<type>([необов'язкові області]): <description>`
> 
> Наприклад:
> 
> `фіксація (навчання): тести за це...під час повторного виклику циклу`

При відкритті Запиту на злиття (PR), ви можете використовувати нижче для визначення типу (можна область (опціонально) і опис.

**Тип:**

| Тип          | Коли вибрати                                                                   |
|:------------ |:------------------------------------------------------------------------------ |
| виправлено   | Змінено або оновили або оновили функціональність, тести, verbiage уроку та ін. |
| подвиг       | Тільки якщо ви додаєте нову функціональність, тести, і т. д.                   |
| тритон       | Зміни, які не відносяться до коду, випробувань чи двозначності уроку.          |
| документація | Зміни на `каталог /docs` або посібник з участі і т. д.                         |

**Область:**

Ви можете вибрати область визначення для [цього списку міток](https://github.com/freeCodeCamp/freeCodeCamp/labels?q=scope).

**Опис:**

Зберігайте його коротко (менше 30 символів) і просто, можете додавати більше інформації в полі опису та коментарях.

Деякі приклади добрих ПРО назв б:

- `фіксований (a11y): покращив контраст панелі пошуку`
- `функція: додавати більше тестів в html і css завдання`
- `fix(api,client): запобігти подачі файлів CORS при подачі форми`
- `документація (i18n): Китайський переклад локальної налаштованої`

## Протилежний запит на злиття

1. Після внесення змін вам буде запропоновано створити запит на злиття на своїй сторінці GitHub.

   ![Зображення - запит на злиття з порівнянням взятим на GitHub](./images/github/compare-pull-request-prompt.png)

2. За замовчуванням усі запити на злиття повинні бути проти головного репозиторію freeCodeCamp , `головної гілки`.

   Переконайтеся, що ваш базовий форк налаштований на freeCodeCamp/freeCodeCamp під час підняття Pull Request.

   ![Зображення - порівняння форків при створенні запиту на злиття](./images/github/comparing-forks-for-pull-request.png)

3. Submit the pull request from your branch to freeCodeCamp's `master` branch.

4. До тіла PR входять більш детальний підсумок внесених вами змін і чому.

   - Вам буде представлено шаблон запросу. Це список який вам слід було залишити перед відкриттям запросу на злиття.

   - Заповніть деталі, які вам підходять. Ця інформація буде розглянута, а рецензенти вирішать, чи буде прийнятий ваш запит на злиття.

   - Якщо призначений PR для вирішення існуючої задачі на GitHub в кінці тіло опису вашого PR, використовувати ключове слово _Закриває_ з номером проблеми до [автоматично закривати цю проблему, якщо PR прийнято і злито](https://help.github.com/en/articles/closing-issues-using-keywords).

     > Приклад: `Закриття #123` задача 123

5. Вкажіть, чи Ви тестували на локальній копії сайту, чи ні.

   Це дуже важливо, коли вносячи зміни, які не просто змінюються на текстовий вміст, такий як документація чи опис проблеми. Приклади змін, які потребують локального тестування включають JavaScript, CSS або HTML, які можуть змінювати функціональність або макет сторінки.

## Зворотній зв'язок з запитами на злиття

> Вітаємо! :tada: у створенні PR і завдяки чому потрібно виділити час, щоб зробити свій внесок.

Наші модератори будуть тепер звертатися за вами та залишати відгук. Будь ласка, будьте терплячі з колегами-модераторами і поважайте їхній час. Усі запити на злиття розглядаються в запланованому курсі.

Якщо вам потрібна допомога, будь ласка, обговоріть в [вітальні](https://gitter.im/FreeCodeCamp/Contributors), ми більше, ніж раді вам допомогти.

> [!TIP] Якщо ви бажаєте внести ще кілька pull requests, ми рекомендуємо вам прочитати, [внести зміни та синхронізувати](https://contribute.freecodecamp.org/#/how-to-setup-freecodecamp-locally?id=making-changes-locally) рекомендацій, щоб не видалити ваш форк.

## Конфлікти на запиту на злиття

Конфлікти можуть виникнути, тому що багато учасників працюють над репозиторієм, і зміни можуть зламати ваш PR, який очікує на перегляд і злиття.

Найчастіше за все, не вам може знадобитися ребаза, тому що ми вирішуємо всі коміти, Однак, якщо тут запитується rebase, що ви повинні зробити.

### Для звичайних помилок та функцій

Коли ви працюєте над регулярними помилками і функціями нашої гілки розробника `майстер`, ви в змозі зробити просту ребазу:

1. Перебудувати вашу локальну копію:

   ```console
   git checkout <pr-branch>
   git pull --rebase master upstream
   ```

2. Вирішити будь-які конфлікти і додати / редагувати коміти

   ```console
   # Або
   git add .
   git commit -m "chore: resolve конфлікти"

   # Або
   git add .
   git commit --amend --no-edit
   ```

3. Натисніть назад зміни до PR

   ```console
   git push --force origin <pr-branch>
   ```

### Для майбутніх навчальних планів та функцій

Коли ви працюєте над функціями для майбутнього навчального плану `наступної*` гілок, ви маєте вирізати вишку:

1. Переконайтеся, що ваш потік повинен бути синхронізованим з вашою локальною:

   ```console
   git checkout master
   git fetch --all --prune
   git checkout next-python-projects
   git reset --hard upstream/next-python-projects
   ```

2. Зробити резервну копію

   а. Або видаліть ваші локальні гілки після створення резервної копії (якщо він ще присутній):

      ```console
      git checkout <pr-branch-name>

      # приклад:
      # git checkout feat/add-numpy-video-question

      git checkout -b <backup-branch-name>

      # приклад:
      # git checkout -b backup-feat/add-numpy-video-question

      git branch -D <pr-branch-name>
      ```

   б. Або просто резервне копіювання гілки pr (якщо ви його не маєте на місцевому рів):

      ```console
      git checkout -b <backup-branch-name> origin/<pr-branch-name>

      # приклад:
      # git checkout -b backup-feat/add-numpy-video-question origin/feat/add-numpy-video-question
      ```

4. Почати з чистого аркуша:

   ```console
   git checkout -b <pr-branch-name> next-python-projects
   git cherry-pick <commit-hash>
   ```

5. Вирішіть будь-які конфлікти і очищення виконання тестів

   ```console
   npm виконується чистий

   npm ci
   npm run test:curriculum --superblock=<superblock-name>

   # приклад:

   # npm run test:curriculum --superblock=python-for-everybody

   ```

6. Якщо все виглядає гарним поштовхом до PR

   ```console
   git push --force origin <pr-branch-name>
   ```
