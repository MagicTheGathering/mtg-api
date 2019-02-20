## 1.32.0 (2019-02-19)
- Ravnica Guild Kit (GK2) added

## 1.31.0 (2018-09-27)
- GRN Added

## 1.30.0 (2018-08-20)
- Commander 2018 (C18) Added

## 1.29.0 (2018-06-12)
- Battlebond (BBD) Added

## 1.28.0 (2018-04-18)
- Elves vs Inventors (DDU) Added
- Dominaria (DOM) Added

## 1.27.0 (2018-03-07)
Masters 25 (A25) Added

## 1.26.1 (2018-01-29)
- Bug fix for booster generation.
- Bug fix for filtering on Urza's Saga.

## 1.26.0 (2018-01-11)
Rivals of Ixalan added (RIX)

## 1.25.0 (2017-12-20)
Unstable and Explorers of Ixalan added

## 1.24.0 (2017-11-16)
DDT and IMA added

## 1.23.0 (2017-09-25)
Ixalan (XLN) Added

## 1.22.0 (2017-08-25)
Commander 2017 (C17) Added

## 1.21.0 (2017-08-20)
Can now filter on `id` and `multiverseid` via URL query parameters.

## 1.20.1 (2017-07-15)
- Split cards fixed

## 1.20.0 (2017-07-11)
- Hour of Devastation (HOU) released

*Note - Patch coming weekend of 7/15-7/16 to address issues with split cards

## 1.19.2 (2017-05-11)
AKH legalities updated

## 1.19.1 (2017-04-24)
The `text` url parameter now supports logical and/or.

Example: `https://api.magicthegathering.io/v1/cards?text=haste,trample,flying`

## 1.19.0 (2017-04-23)
- Duel Decks: Mind vs. Might (late)
- Amonkhet (AKH) released

## 1.18.0 (2017-03-20)
Modern Masters 2017 (mm3) Released

## 1.17.1 (2017-02-02)
- Fixed CHK flip cards
- Fixed KLD, AER block information
- Fixed Release date for UNH

## 1.17.0 (2017-01-17)
Sets Added:
- PCA (Planchase Anthology)
- AER (Aether Revolt)

## 1.16.4 (2017-01-04)
Fixes issue with using the orderBy parameter with cmc or other integer like strings (power, toughness)

Adds the ability to filter sets by their type, such as core or expansion.

## 1.16.3 (2017-01-02)
Adds ability to filter on cards that contain a specific field.

For example: `https://api.magicthegathering.io/v1/cards?contains=imageUrl`

## 1.16.2 (2016-12-29)
Fixed bug with filtering on foreign name that contains an apostrophe.

## 1.16.1 (2016-12-01)
Added a new query parameter that allows a user to retrieve cards randomly. Examples below:

#### One random card
`https://api.magicthegathering.io/v1/cards?pageSize=1&random=true`

#### 10 random rares
`https://api.magicthegathering.io/v1/cards?pageSize=10&random=true&rarity=rare`

## 1.16.0 (2016-11-16)
Commander 2016 added. (c16)

## 1.15.2 (2016-10-25)
Fixes issue with filtering on the name of a card that contains a comma. The comma was still being recognized as a delimited, when that parameter does not allow logical AND operators, only the logical OR (|).

## 1.15.1 (2016-10-23)
Fixes #14. Wizards has stopped using the Æ symbol in card names in favor of "Ae", with errata.

## 1.15.0 (2016-10-14)
New endpoint for game formats added:

`https://api.magicthegathering.io/v1/formats`

The 'colorIdentity' field has also been added to the Card resource.

## 1.14.4 (2016-10-13)
Kaladesh standard. DTK and ORI dropped from standard.

*Note - this update was a bit slower due to issues with mtgjson. This update DOES introduce issues with flip cards which will have to be patched.

https://github.com/mtgjson/mtgjson/issues/240

## 1.14.3 (2016-10-02)
Fixes bug #9 - filtering by layout

## 1.14.2 (2016-10-01)
Updated Access-Control-Expose-Headers in response to include custom headers. This should fix issues with CORS and trying to access custom headers.

## 1.14.1 (2016-09-25)
Added support for partial name matching on foreign names:

Partial match:
`https://api.magicthegathering.io/v1/cards?name=aplastacráneos&language=spanish&set=ktk`

Exact match:
`https://api.magicthegathering.io/v1/cards?name="zurgo aplastacráneos"&language=spanish&set=ktk`

## 1.14.0 (2016-09-21)
Added Set: Kaladesh (KLD)

## 1.13.5 (2016-09-19)
`orderBy` query string parameter now supported. Example:

`https://api.magicthegathering.io/v1/cards?set=emn&orderBy=cmc`

## 1.13.4 (2016-09-18)
Fields that contain arrays (like colors) can now be filtered on exactly. For example:

`https://api.magicthegathering.io/v1/cards?colors="red,blue"`

The request above will search for cards that ONLY have the colors Red and Blue. That is, cards with Red, Blue, and another color will not be returned.

| Request | Description|
|---------|------------|
|`https://api.magicthegathering.io/v1/cards?colors="red,blue"` | Cards that only have the colors Red and Blue |
|`https://api.magicthegathering.io/v1/cards?colors=red,blue` | Cards that at least have the colors Red and Blue |
|`https://api.magicthegathering.io/v1/cards?colors=red|blue` | Cards that at least contain either Red or Blue |

## 1.13.3 (2016-09-10)
The __id__ field is now supported when requesting a single card.

For example, previously you could request Zurgo Helmsmasher by its multiverseid with this endpoint:

`https://api.magicthegathering.io/v1/cards/386380`

Now, you can also request the same card using the __id__ field:

`https://api.magicthegathering.io/v1/cards/c0a202d529f57bc6e83cce412850a91dadd050d1`

This is important because some cards do not have a multiverseid, but every card has an __id__. Support for multiverseid is staying in version 1 of the API, but will most likely be removed from version 2. Because of this, it is __HIGHLY RECOMMENDED__ to use the __id__ field from this point on when requesting a specific card.

## 1.13.2 (2016-08-29)
Added sets:
- From the Vault: Lore
- Conspiracy: Take the Crown

## 1.13.1 (2016-08-24)
Bug fix for filtering on sets by name. Querying for sets with an apostrophe no longer returns a 500 error. Set names with an apostrophe will also no longer have two single quotes in the response.

## 1.13.0 (2016-08-12)
- Minor performance improvements
- Multiple new response headers added:

1. Link: Link headers with prev, last, next, first links (when appropriate)
2. Page-Size: The page size for the request
3. Count: The amount of elements returned
4. Total-Count: The total number of elements (all pages)
5. Ratelimit-Limit: The ratelimit for a given user
6. Ratelimit-Remaining: The number of requests left before the ratelimit is exceeded.

Examples:

```
Link: <http://api.magicthegathering.io/v1/cards?page=311>; rel="last", <http://api.magicthegathering.io/v1/cards?page=2>; rel="next"
Page-Size: 100
Count: 100
Total-Count: 31090
Ratelimit-Limit: 5000
Ratelimit-Remaining: 4999
```

## 1.12.5 (2016-08-10)
Temporarily changed pageSize limit to 100 due to overloaded server issues.

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
