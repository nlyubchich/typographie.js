#Typographie.js &nbsp;[![Build Status](https://travis-ci.org/asleepwalker/typographie.js.svg?branch=master)](https://travis-ci.org/asleepwalker/typographie.js)

Library for preparation of russian texts to web publication.<br>
Core of [Typographie](http://typographie.ru/) web service.

## Installation

Via npm:

	npm install typographie --save

Via Bower:

	bower install typographie --save

## Example

```
var Typographie = require('typographie');
var engine = new Typographie(['inquot', 'dashes', 'specials', 'paragraphs']);

var raw = 'Сервис "Typographie" - подготовка текстов к веб-публикации онлайн (с) 2014-2017';
var result = engine.process(raw);

console.log(result);
// > Сервис «Typographie» — подготовка текстов к веб-публикации онлайн © 2014–2017
```

## Actions

`quotes` : Correction of quotes: "" becomes «».<br>
`inquot` (needs `quotes`) : Nested quotes: «„“» (otherwise — duplicate quotes stashing).<br>
`dashes` : If necessary replace hyphens with dashes and minus signs.<br>
`angles` : Replace asterisks and quotes with degrees, feet, inches.<br>
`dblspace` : Fix duplicate spaces in the text.<br>
`specials` : Insert special characters (from the symbol table).<br>
`mathchars` : Insert mathematical symbols (from the same table).<br>
`punctuation` : Fix punctuation, such as spaces before commas.<br>
`specialspaces` : Fix the wrong skip special characters with spaces.<br>
`nbsp` : Attach short words to following words in the text.<br>
`hellip` : Replace repeating dot symbols with ellipsis.<br>
`paragraphs` : Puts paragraphs (&lt;p&gt;) when converting to HTML (with empty string as a delimeter).

The list should be passed as array, e.g. `['action1', 'action2', 'action3']`.

## License

The MIT License.
