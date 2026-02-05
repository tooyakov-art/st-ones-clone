---
name: localize-kz
description: Localize a website for Kazakhstan - replace Russian contacts, currency, addresses with Kazakh placeholders
---

# Localize Website for Kazakhstan

Replace all Russian-specific content with Kazakh equivalents:

## Replacements to make:

1. **Address:** Moscow addresses -> Almaty placeholder
   - "г.Москва, ..." -> "г.Алматы, ул. Достык 123, оф. 45"

2. **Phone:** Russian numbers -> Kazakh format
   - "+7 9XX ..." -> "+7 777 123-45-67"

3. **Currency:** Rubles -> Tenge
   - "₽" or "&#8381;" -> "₸"
   - Keep same numbers (prices are similar range)

4. **Social media:** Replace with placeholders
   - Instagram/Telegram/VK links -> "#instagram", "#telegram", "#vk"

5. **Logo:** Add CSS placeholder
   - Hide original logo image
   - Show "ВАШ ЛОГОТИП" placeholder badge

6. **Brand name:** Replace with client placeholder or "Алтын"

Use sed with find to batch replace across all HTML files.
