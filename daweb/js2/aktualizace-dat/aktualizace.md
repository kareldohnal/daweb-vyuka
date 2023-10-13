## Aktualizace obsahu stránky

V této části se opět vrátíme k naší aplikaci s nákupními seznamy. V předchozí části jsme sice komponentu `ListItem` uděleli hezky interaktivní a můžeme v ní označovat položky jako koupené, ale zaškrtnutí položky se projeví pouze na frontendu. Když stránku obnovíme, vrátí se seznam do stavu, v jakém je na backendu. Budeme tedy změnu zaškrnutí chtít odeslat na server.

Abychom mohli různými způsoby měnit data na serveru, potřebujeme několik dalších metod pro naše HTTP požadavky. V předchozí částí jsme viděli metodu POST. Běžně se dále používají metody PUT a DELETE. Jejich významy jsou následující:

- GET: slouží k načtení dat (seznamu nebo detailu jedné položky)
- POST: slouží k přidání nového prvku do kolekce,
- PUT: slouží ke změně (přepsání) už existujícího prvku,
- DELETE: slouží k odstranění prvku z kolekce.

Většina backendových API funguje tak, že když nějakým požadavkem změníme data na serveru, jako odpověď přijdou aktualizovaná data, která pak můžeme rovnou zobrazit. Když tedy změníme zaškrtnutí položky, server nám jako odpověď pošle objekt s aktualizovanou položkou, kterou vykreslíme opět pomocí komponenty `ListItem`.

### Implementace

Vyjdeme z [poslední verze](https://github.com/Czechitas-podklady-WEB/prvni-komponenta/tree/dom-elementy) našeho nákupního seznamu.

V našem příkladu nejdříve musíme přejít na nové API na adrese

```
https://apps.kodim.cz/daweb/shoplist/api
```

Naše staré tréninkové API totiž neumí aktualizovat data na serveru.

Při stisknutí zaškrtávacího tlačítka odešleme PUT požadavek, který pošle na server znovu celou položku seznamu, která bude mít odpovídajícím způsobem nastaveno zaškrtnutí či nezaškrtnutí položky. Kód tlačítka uvnitř komponenty `ListItem` pak bude vypadat takto:

```js
element.querySelector('button').addEventListener('click', () => {
  const resp = await fetch(`https://apps.kodim.cz/daweb/shoplist/api/weeks/0/days/mon/${id}`, {
    method: 'PUT',
    headers: {
      'Content-Type': 'application/json',
    },
    body: JSON.stringify({
      product,
      amount,
      done: !done
    }),
  })
  const data = await resp.json())
  //TODO location =
});
```

Nyní si můžeme vyzkoušet, že po obnovení stránky náš seznam bude už ve správném stavu podle toho, jak s ním interagujeme na frontendu.

Kód celé aplikace najdete ve větvi [posilani-dat](https://github.com/Czechitas-podklady-WEB/prvni-komponenta/tree/posilani-dat) repozitáře s nakupním seznamem.