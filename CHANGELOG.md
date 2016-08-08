## 1.12.4 (2016-08-07)
Updated legalities for Eldritch Moon

## 1.12.3 (2016-08-06)
Game format and legality can now be filtered on.

###Get all cards banned from Commander format

`https://api.magicthegathering.io/v1/cards?gameFormat=commander&legality=banned`

###Get all cards that are legal in Standard format

`https://api.magicthegathering.io/v1/cards?gameFormat=standard`

## 1.12.2 (2016-08-05)
The 'Sets' resource can now be filtered via the 'block' url parameter.

###Match a block name exactly (not case sensitive):

`https://api.magicthegathering.io/v1/sets?block="Battle for Zendikar"`

###Match one or more block names (comma delimited, partial matching)

`https://api.magicthegathering.io/v1/sets?block=zendikar,shadows`

## 1.12.1 (2016-07-25)
Fixes issue #4

## 1.12.0 (2016-07-16)
Added set: Eldritch Moon (EMN)

## 1.11.0 (2016-06-09)
Added set: Eternal Masters (EMA)
