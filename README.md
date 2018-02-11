# GUS API - PHP
Prosta klasa PHP, korzystająca z GUS API w celu pobrania danych firmy (adresy itp) po podaniu numeru NIP.

## Działanie
Na początek należy zamienić adresy produkcyjne z adresami testowymi.
```php
    //adresy produkcyjne
    protected $loginUrl = 'https://wyszukiwarkaregon.stat.gov.pl/wsBIR/UslugaBIRzewnPubl.svc/ajaxEndpoint/Zaloguj';
    protected $searchDataUrl = 'https://wyszukiwarkaregon.stat.gov.pl/wsBIR/UslugaBIRzewnPubl.svc/ajaxEndpoint/daneSzukaj';
    //adresy testowe
    protected $loginTestUrl = 'https://wyszukiwarkaregontest.stat.gov.pl/wsBIR/UslugaBIRzewnPubl.svc/ajaxEndpoint/Zaloguj';
    protected $searchDataTestUrl = 'https://wyszukiwarkaregontest.stat.gov.pl/wsBIR/UslugaBIRzewnPubl.svc/ajaxEndpoint/daneSzukaj';
```
Kolejnym krokiem jest zmienienie klucza dostępu do GUS na prawidłowy uzyskany z GUS.
```php
protected $key = "abcde12345abcde12345";
```
Po wykonaniu tych czynności, wystarczy, że utworzymy obiekt GusRegonApi i odwołamy się do metody checkNip podając w parametrze NIP.

```php
$nip = 'tutaj_numer_nip';
$gus = new GusRegonApi();
$result = $gus->checkNip($nip);
```
