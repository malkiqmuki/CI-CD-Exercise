# 🔄 CI/CD Exercise

![CI](https://github.com/malkiqmuki/CI-CD-Exercise/actions/workflows/CIPipeline.yml/badge.svg)

Това репо демонстрира CI/CD концепции и автоматизация.

## 📖 Описание
Това репо демонстрира основни концепции за **Continuous Integration (CI)** и **Continuous Delivery/Deployment (CD)**.  
Целта е да се покаже:
- Как се изгражда и тества проект автоматично
- Как се използват **GitHub Actions** (или друг pipeline инструмент)
- Как се прилага добър workflow за екипна работа

---

## 🛠️ Използвани технологии
- **GitHub Actions** – автоматизация на build и тестове
- **Node.js / Java / Python** – (замени с твоя език за проекта)
- **Docker** – (по избор, за контейнеризация)
- **Unit/Integration тестове** – за проверка на функционалностите
- **GitHub** – за версия контрол и CI/CD pipeline

---

## 🚀 Как работи
1. **CI стъпки:**
   - Инсталиране на зависимости
   - Стартиране на Unit тестове
   - Проверка на code style и качество (linting)
2. **CD стъпки (ако има):**
   - Build на проект
   - Деплой на тестова среда
   - (По избор) Автоматичен деплой на продукция

---


## 🔍 Примерен GitHub Actions Workflow
```yaml
name: CI Pipeline

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build-and-test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Set up Node.js
        uses: actions/setup-node@v3
        with:
          node-version: "18"

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test

✅ Ползи

Демонстрация на автоматизация на тестовете
Показва умения по DevOps практики
Лесен за разширяване с линтери, Docker, deployment стъпки


🔥 Идеи за надграждане

Добавяне на Code Coverage Reports
Автоматично генериране на Docker образи
Интеграция със Slack/Teams за известия
Deployment към облачна платформа (Heroku, AWS, Azure)

👨‍💻 Автор
GitHub: malkiqmuki
