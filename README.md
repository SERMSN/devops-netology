# Это мой репозиторий для курса по DevOps от Netology.

---

## Шаг 1: Создание и клонирование репозитория

1. Создан публичный репозиторий `devops-netology` на GitHub с галочкой "Add a README.md".
2. Репозиторий успешно создан. GitHub автоматически создал первый коммит "Initial commit".
3. Репозиторий клонирован на локальную машину с использованием протокола HTTPS:
```bash
git clone https://github.com/SERMSN/devops-netology.git
cd devops-netology
```

---

## Шаг 2: Первоначальная настройка Git

Выполнена настройка глобальных параметров Git:
```bash
git config --global user.name "Malyavko Sergei"
git config --global user.email "sermsn@gmail.com"
```

Проверка статуса репозитория:
```bash
git status
```

---

## Шаг 3: Первый коммит ("First commit")

1. Файл `README.md` отредактирован:
```markdown
# devops-netology
Repository for Netology DevOps course
```

2. Выполнены команды для просмотра изменений:
```bash
git status
git diff
```

3. Файл добавлен в staged и закоммичен:
```bash
git add README.md
git diff --staged
git commit -m "First commit"
```

---

## Шаг 4: Второй коммит ("Added gitignore")

1. Созданы файлы `.gitignore`:
```bash
touch .gitignore
mkdir terraform
touch terraform/.gitignore
```

2. Файл `terraform/.gitignore` заполнен содержимым

3. В `README.md` добавлено описание:

## Файлы, игнорируемые в `.gitignore` для Terraform

Будут игнорироваться следующие типы файлов:

### 1. **Локальные директории Terraform**
```
.terraform/
```
Игнорируется вся директория `.terraform/` и все её содержимое в любом месте репозитория.

### 2. **Файлы состояний Terraform**
```
*.tfstate
*.tfstate.*
```
Игнорируются:
- Все файлы с расширением `.tfstate` (например: `terraform.tfstate`)
- Все файлы, начинающиеся с любого имени и содержащие `.tfstate.` в любой части имени (например: `terraform.tfstate.backup`)

### 3. **Файлы логов аварийных завершений**
```
crash.log
crash.*.log
```
Игнорируются:
- Файл с точным именем `crash.log`
- Файлы, начинающиеся с `crash.`, затем содержащие любой текст, и заканчивающиеся на `.log` (например: `crash.12345.log`)

### 4. **Файлы переменных Terraform**
```
*.tfvars
*.tfvars.json
```
Игнорируются:
- Все файлы с расширением `.tfvars` (например: `terraform.tfvars`)
- Все файлы с расширением `.tfvars.json` (например: `variables.tfvars.json`)

### 5. **Файлы переопределений**
```
override.tf
override.tf.json
*_override.tf
*_override.tf.json
```
Игнорируются:
- Файлы с точными именами `override.tf` и `override.tf.json`
- Файлы, заканчивающиеся на `_override.tf` (например: `my_override.tf`)
- Файлы, заканчивающиеся на `_override.tf.json` (например: `custom_override.tf.json`)

### 6. **Файлы блокировок состояний**
```
.terraform.tfstate.lock.info
```
Игнорируется файл с точным именем `.terraform.tfstate.lock.info`

### 7. **Файлы конфигурации CLI**
```
.terraformrc
terraform.rc
```
Игнорируются файлы с точными именами `.terraformrc` и `terraform.rc`

4. Выполнен коммит:
```bash
git add .gitignore terraform/.gitignore README.md
git commit -m "Added gitignore"
```

---

## Шаг 5: Третий коммит ("Prepare to delete and move")

1. Созданы временные файлы:
```bash
echo "will_be_deleted" > will_be_deleted.txt
echo "will_be_moved" > will_be_moved.txt
```

2. Файлы добавлены и закоммичены:
```bash
git add will_be_deleted.txt will_be_moved.txt
git commit -m "Prepare to delete and move"
```

---

## Шаг 6: Четвертый коммит ("Moved and deleted")

1. Выполнены операции удаления и перемещения:
```bash
git rm will_be_deleted.txt
git mv will_be_moved.txt has_been_moved.txt
```

2. Изменения закоммичены:
```bash
git commit -m "Moved and deleted"
```

---

## Шаг 7: Проверка истории коммитов

Просмотр истории коммитов:
```bash
git log --oneline
```

---

## Шаг 8: Отправка изменений на GitHub

Выполнена отправка всех коммитов в удаленный репозиторий:
```bash
git push origin main
```

---

## Финальная проверка

1. **Репозиторий на GitHub:** [https://github.com/SERMSN/devops-netology](https://github.com/SERMSN/devops-netology)

2. **Вкладка Commits:** Отображаются все 5 коммитов

---

## Вывод

Задание выполнено в соответствии с требованиями:
- ✅ Создан репозиторий с README.md
- ✅ Выполнена настройка Git
- ✅ Создано 4 коммита + Initial Commit
- ✅ Настроен .gitignore для Terraform
- ✅ Выполнены операции с файлами (создание, удаление, перемещение)
- ✅ Все изменения отправлены на GitHub