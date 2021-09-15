# Решение "Git: Практический курс" в консоли

## 1. Создание репозитория на GitHub

```
// Создаём репозиторий через веб-интерфейс GitHub
```

## 2. Первый коммит в мастер

```
git clone git@github.com:simakov-a/TrainingRepository_Simakov.git
cd TrainingRepository_Simakov
// Cоздаём файл file1.txt
git add file1.txt
git commit -m "Мой первый коммит"
git push
```

## 3. Реверт коммита

```
git revert 13f4c67
git push
```

## 4. Новая ветка

```
git branch develop
git push -u origin develop
```

## 5. Мерж веток

```
git checkout develop
// Cоздаём файл с именем file2.txt
git add file2.txt
git commit -m "Мой второй коммит"
git checkout main
git merge develop
git push
```

## 6. Перенос коммита из одной ветки в другую (cherry-pick)

```
git checkout develop
git add DailyBonus.xml
git commit -m "Добавить DailyBonus.xml"
git push
git checkout main
git cherry-pick f833142
git push
```

## 7. Разрешение конфликтов

```
git checkout develop
// Заменяем уже имеющийся в папке репозитория файл DailyBonus.xml
git add DailyBonus.xml
git commit -m "Заменить DailyBonus.xml в develop"
git push

git checkout main
// Заменяем уже имеющийся в папке репозитория файл DailyBonus.xml
git add DailyBonus.xml
git commit -m "Заменить DailyBonus.xml в main"
git push

git merge develop
// Возникшие конфликты разрешаем в сторону мастер
git add DailyBonus.xml
git commit -m "Сливаем с разрешением кофликта в DailyBonus.xml в пользу master"
git push
```

## 8. Создание Pull Request

```
git checkout develop
// ABTests.xml закоммитить в ветку develop
git add ABTests.xml
git commit -m "Добавляем ABTests.xml в develop"
git push
// Создаём pull request через веб-интерфейс GitHub
```

## 9. Merge Pull Request в мастер

```
// Смержить реквест в мастер через Rebase and Merge в веб-интерфейсе GitHub.
git checkout main
git pull
```

## 10. Подключение submodule

```
git submodule add git@github.com:simakov-a/SubmoduleRepository_Simakov.git
git commit -am "Добавил подмодуль"
git push
```

## 11. Коммит в submodule

```
cd SubmoduleRepository_Simakov
// Cоздаём файл file1.txt в подмодуле SubmoduleRepository
git add file1.txt
git commit -m "Мой первый коммит в сабмодуле"
git push
cd ..
git commit -am "Внесли изменения в сабмодуле"
git push
```
