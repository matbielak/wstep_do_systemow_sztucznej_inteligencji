# Prolog

## Zadanie 1
* A - rodzenstwo
* B - kuzynowstwo
* C - tesciowie
* D - inny rodzic rodzenstwa
* E - rodzeństwo przyrodnie
* F - malzonek rodzenstwa
* G - sytuacja z Ukrytej Prawdy

## Zadanie 2
Na starcie mamy predykaty:
* rodzic
* mezczyzna
* osoba

kobieta(X) :- 
    osoba(X),
    /= mezczyzna(X).
 
ojciec(X,Y) :- 
    osoba(Y),
    mezczyzna(X),
    rodzic(X,Y).
   
