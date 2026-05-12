# Щедрий вісник 2025 — Дизайн-платформа

Self-contained static website для показу клієнту: бренд-система,
4 варіанти стилістики, хід роботи над брошурою.

## Структура

```
deploy/
├── index.html           # Огляд проєкту
├── ui-kit.html          # Бренд-система (палітра, шрифти, патерни, мотиви)
├── variants.html        # 4 варіанти стилістики з PDF
├── process.html         # Хід роботи, тайм-лайн, матеріали
├── styles.css           # Стилі
├── fonts/               # Inter + e-Ukraine Head (бренд-шрифти)
├── logos/               # SVG логотипи Щедрика (color/black/white × horizont/vertical × ua/en)
├── patterns/            # 3 брендові патерни (white/cyan/black)
└── variants/            # PDF + PNG прев'ю всіх 4 варіантів
```

## Деплой на GitHub Pages

1. Створи новий публічний репозиторій на GitHub (наприклад, `schedryk-visnyk-preview`).
2. У цій папці `deploy/` ініціалізуй git і запуш:
   ```bash
   cd deploy
   git init
   git add .
   git commit -m "Initial preview site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```
3. У GitHub: **Settings → Pages → Source: Deploy from branch → Branch: main / (root)**.
4. Через ~30 секунд сайт доступний за `https://<your-username>.github.io/<repo-name>/`.
5. Скинь лінк замовнику.

## Локальний перегляд

Просто відкрий `index.html` у браузері — все працює як статичний сайт.
Або запусти простий сервер:
```bash
cd deploy
python -m http.server 8000
# http://localhost:8000
```

## Перебудова сайту

З папки проєкту:
```bash
python scripts/build_deploy.py
```
Скрипт пересоберає `deploy/` з актуальних файлів `web/`, `assets/`, `src/out/variants/`.

---

**БО «Благодійний Фонд Щедрик»** · «Щедрий вісник 2025»
Дизайн та верстка: Valentyn Ihnatov
