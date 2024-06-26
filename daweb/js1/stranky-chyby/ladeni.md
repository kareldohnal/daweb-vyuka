## Ladění programů

Procesu hledání a opravování chyb v programech se obecně říká :term{cs="ladění" en="debugging"}.
Situace, kdy náš program napíšeme tak, že nedělá, co chceme, je zcela v pořádku. Nikdo v praxi nedokáže na první dobrou napsat větší program bez chyby. Čím jsou však naše programy větší a složitější, tím roste prostor pro stále záludnější a hůře odhalitelné chyby.

### console.log

Ladění programů je neodmyslitelnou součástí vývoje v JavaScriptu. Když narazíte na chybu ve svém kódu, musíte ji najít a opravit. Jedním z nejběžnějších nástrojů pro ladění v JavaScriptu je `console.log`.

`console.log` je metoda v JavaScriptu, kterou můžete použít k výpisu informací do konzole prohlížeče. Tato metoda je užitečná pro sledování hodnot proměnných, zjištění, kterou částí kódu program prošel nebo zda byla volána naše funkce, a pro zobrazení různých zpráv, které vám pomohou identifikovat chyby ve vašem kódu.

### Možnosti ladění

Velmi brzy už je program tak dlouhý a komplikovaný, že nejsme schopni chybu najít pouze tím, že si po sobě čteme svůj kód. Nedej bože, pokud navíc před sebou nemáme kód vlastní, nýbrž kód kolegy, který již dávno opustil firmu, a svému kódu rozuměl pouze on. V takovou chvíli máme v podstatě několik možností, co můžeme dělat.

1. Zkoušet náhodně měnit různé části kódu – místo kulatých závorek dát hranaté, místo `===` dát `==` apod. Toto je velmi zoufalý a naivní přístup, který spíš ukazuje, že dostatečně nerozumíte tomu, co JavaScript runtime dělá a jak funguje. Velmi doporučju se tomuto postupu vyhnout a naopak se snažit porozumět tomu, co program dělá.
1. Zahrát si na počítač, číst kód řádek po řádku a v hlavě si představovat, co JavaScript runtime dělá. Toto je však možné spíš u kratších kusů kódu, ve složitějším programu nemáte šanci udržet v hlavě najednou všechny informace, které průběh programu ovlivňují.
1. Velmi užitečná varianta je na vhodná místa v kódu přidat volání `console.log`, a budete do konzole vypisovat informace, které jsou v daném místě důležité. Program proběhne beze změny, ale v konzoli po něm zůstane „stopa“, informace, které vypsal.
1. Poslední možnost je použít ladící nástroje v developer tools, kdy můžete prohlížeč donutit, aby kód opravdu procházel řádek po řádku, za každým řádkem se zastavil a vy se můžete podívat, co je v které proměnné. To je však už o dost komplikovanější a bohužel tuhle metodu nejde použít vždy.
