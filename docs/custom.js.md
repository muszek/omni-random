To jest dokumentacja do naszego custom.js.  Pisana przez nie-programistę dla nie-programistów. Zastanawiam się, od której strony to ugryźć - czy opisywać metody, czy od drugiej strony - opisywać, jak ogarnąć konkretne problemy. Pewnie zacznę od opisu metod, a na koniec ugryzę problemy.

## omni.define

Pozwala obliczyć wartość jakiejś zmiennej przy pomocy javascriptu (a nie gołym wzorem matematycznym). To jest rozwiązanie jednokierunkowe - możemy obliczyć tylko jedną ze zmiennych (nie policzymy niczego w innych kierunkach... ale kiedyś to umożliwimy).

Przykładowe wywołanie (tam, gdzie wklepujemy wzory): ```gamma = get_something(alpha, beta);```

Przykładowe użycie:

```
omni.define('get_something', function(alpha, beta) { // nazwy zmiennych nie muszą być tożsame z nazwami zmiennych z wywołania
	var a = alpha.toNumber(); // zamieniam obiekt mathjs na zwykłą liczbę (bo tak łatwiej, a tu mi ta super precyzja z reguły jest mi niepotrzebna)
	var b = beta.toNumber();
	
	if(a > 5) { // dla wartosci a wiekszych od 5 zwracamy wartosc b/2
		return b / 2; // AFAIR można zwrócić zwykłą liczbę (jak tutaj... upewnij się z Danielem), lub obiekt mathjs (wtedy dałbym return mathjs.number(b/2))
	} else { // w pozostalych przypadkach zwracamy c
		return b;
	}
});
```
