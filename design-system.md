# Design System — inakshi.in.ua

## Шрифти

```html
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@400;700;900&family=Plus+Jakarta+Sans:wght@300;400;500;600;700&display=swap" rel="stylesheet">
```

- `Unbounded` — h1, h2, логотип, акцентні слова
- `Plus Jakarta Sans` — h3, body, кнопки, підписи

## Кольори

```css
:root {
  /* Основні */
  --color-bg:        #FAFAF8;   /* теплий білий фон */
  --color-surface:   #F2F0EB;   /* картки, секції */
  --color-text:      #1A1A2E;   /* основний текст */
  --color-text-mute: #6B6B80;   /* підписи, мета */

  /* Акцентні */
  --color-primary:   #5B4FCF;   /* індиго — довіра, глибина */
  --color-secondary: #E8A838;   /* бурштин — тепло, енергія */
  --color-accent:    #E05A6B;   /* корал — увага, емоція */

  /* Утиліти */
  --color-border:    #E2E0D8;
  --color-white:     #FFFFFF;
}
```

**Логіка кольорів:**
- Індиго `#5B4FCF` — professional trust, CTA-кнопки, заголовки
- Бурштин `#E8A838` — тепло, підсвічення, декор
- Корал `#E05A6B` — емоційні акценти, важливі факти

## Відступи

```css
:root {
  --space-xs:  8px;
  --space-sm:  16px;
  --space-md:  32px;
  --space-lg:  64px;
  --space-xl:  96px;
  --space-2xl: 140px;
}
```

## Типографіка

```css
h1 { font-family: 'Unbounded'; font-size: clamp(2.4rem, 5vw, 5rem); font-weight: 900; line-height: 1.1; }
h2 { font-family: 'Unbounded'; font-size: clamp(1.8rem, 3.5vw, 3.2rem); font-weight: 700; line-height: 1.2; }
h3 { font-family: 'Plus Jakarta Sans'; font-size: clamp(1.1rem, 2vw, 1.5rem); font-weight: 600; }
p  { font-family: 'Plus Jakarta Sans'; font-size: clamp(1rem, 1.5vw, 1.15rem); line-height: 1.7; }
```

## Кнопки

```css
.btn-primary {
  background: var(--color-primary);
  color: #fff;
  font-family: 'Plus Jakarta Sans'; font-weight: 600;
  padding: 16px 36px; border-radius: 50px;
  transition: transform .2s, box-shadow .2s;
}
.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 32px rgba(91,79,207,.35);
}

.btn-secondary {
  background: transparent;
  border: 2px solid var(--color-primary);
  color: var(--color-primary);
  padding: 14px 34px; border-radius: 50px;
}
```

## Анімації при скролі

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) e.target.classList.add('visible');
  });
}, { threshold: 0.15 });

document.querySelectorAll('.fade-up').forEach(el => observer.observe(el));
```

```css
.fade-up {
  opacity: 0;
  transform: translateY(24px);
  transition: opacity .7s ease, transform .7s ease;
}
.fade-up.visible {
  opacity: 1;
  transform: translateY(0);
}
```

## Сітка

```css
.container {
  width: 100%;
  max-width: 1240px;
  margin: 0 auto;
  padding: 0 var(--space-md);
}
```

## Структура блоків

| Блок | Файл | Статус |
|---|---|---|
| Hero | blocks/hero.html | ✓ |
| Проблема | blocks/problem.html | — |
| Хто ми | blocks/about.html | — |
| Послуги | blocks/services.html | — |
| Як це працює | blocks/how-it-works.html | — |
| Відгуки | blocks/testimonials.html | — |
| CTA | blocks/cta.html | — |
