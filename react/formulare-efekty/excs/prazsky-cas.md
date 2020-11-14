---
title: Pražský čas
demand: 2
---

1. Založte si novou React aplikaci podle klasického [starteru](https://github.com/Czechitas-podklady-WEB/project-starter/archive/react-starter.zip)
1. Založte komponentu `App` a uvnitř vytvořte jednoduchý efekt, který se spustí pří prvním zobrazení komponenty. Uvnitř tohoto efektu zavolejte funkci `alert` a zobrazte vyskakovcí okno s nějakou zprávou.
1. Přidejte do vaší komponenty stav `datetime`, jehož výchozí hodnota bude `null`. Ve vašem efektu smažte volání `alert` a uložte do stavu čas jako řetězec ve formátu

   ```
   '2020-11-13T22:46';
   ```

   Zobrazte váš čas někde na stránce a vyzkoušejte, že váš efekt správně nastaví stav při prvním zobrazení komponenty.

1. Upravte váš efekt tak, aby pomocí volání `fetch` získal aktuální datum a čas pro časovou zónu `Europe/Prague`. Hodnotu získáte na API endpointu

   ```
   http://worldtimeapi.org/api/timezone/Europe/Prague
   ```

   pod položkou `datetime`. Získanou hodnotu uložte do stavu a vyzkoušejte, že vaše aplikace funguje.