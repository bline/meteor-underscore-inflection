# Meteor Underscore Inflection

underscore.inflection repackaged for Meteor

Thanks to Jeremy Ruppel for the library:
(https://github.com/jeremyruppel/underscore.inflection)

Excerpts from the original README follow.

=====


Inflections
-----------

The methods listed below are the ones you'll be using 99% of the time.

### pluralize

**Signature:** `_.pluralize( word )`

`pluralize` pluralizes the string passed to it.

	// functional style
	_.pluralize( 'word' ); // => 'words'
	
	// object-oriented style
	_( 'word' ).pluralize( ); // => 'words'

It also can accept a number as the second parameter. If a number is provided, it will pluralize the word to match the number.

	_( 'word' ).pluralize( 0 ); // => 'words'
	_( 'word' ).pluralize( 1 ); // => 'word'
	_( 'word' ).pluralize( 1.5 ); // => 'words'
	
Optionally, you can pass `true` as a third parameter. If found, this will include the count with the output.

	_( 'word' ).pluralize( 0, true ); // => '0 words'
	_( 'word' ).pluralize( 1, true ); // => '1 word'

### singularize

**Signature:** `_.singularize( word )`

`singularize` returns the singular version of the plural passed to it.

	// functional style
	_.singularize( 'words' ); // => 'word'
	
	// object-oriented style
	_( 'words' ).singularize( ); // => 'word'
	
### gsub

**Signature:** `_.gsub( word, rule, replacement )`

`gsub` is a method that is just slightly different than our standard `String#replace`. The main differences are that it matches globally every time, and if no substitution is made it returns `null`. It accepts a string for `word` and `replacement`, and `rule` can be either a string or a regex.

	// functional style
	_.gsub( 'word', /wo/, 'ne' ); // => 'nerd'
	
	// object-oriented style
	_( 'word' ).gsub( /wo/, 'ne' ); // => 'nerd'

Configuring the Inflector
-------------------------

Should you ever need to configure the Inflector beyond the defaults, use these methods to do so:

### plural

**Signature:** `_.plural( rule, replacement )`

`plural` creates a new pluralization rule for the inflector. `rule` can be either a string or a regex.

	// functional style with explicit string
	_.plural( 'axis', 'axes' );
	
	// object-oriented style with explicit string
	_( 'axis' ).plural( 'axes' );

	// functional style with regex
	_.plural( /(ax)is$/i, '$1es' );
	
	// object-oriented style with regex
	_( /(ax)is$/i ).plural( '$1es' );
	
### singular

**Signature:** `_.singular( rule, replacement )`

`singular` creates a new singularization rule for the inflector. `rule` can be either a string or a regex.

	// functional style with explicit string
	_.plural( 'data', 'datum' );

	// object-oriented style with explicit string
	_( 'data' ).plural( 'datum' );

	// functional style with regex
	_.plural( /(t)a$/i, '$1um' );

	// object-oriented style with regex
	_( /(t)a$/i ).plural( '$1um' );

### irregular

**Signature:** `_.irregular( singular, plural )`

`irregular` is a shortcut method to create both a pluralization and singularization rule for the word at the same time. You must supply both the singular form and the plural form as explicit strings.

	// functional style
	_.irregular( 'haxor', 'hax0rs!' );
	
	// object-oriented style
	_( 'haxor' ).irregular( 'hax0rs!' );
	
### uncountable

**Signature:** `_.uncountable( word )`

`uncountable` creates a new uncountable rule for `word`. Uncountable words do not get pluralized or singularized.

	// functional style
	_.uncountable( 'equipment' );
	
	// object-oriented style
	_( 'equipment' ).uncountable( );
	
### resetInflections

**Signature:** `_.resetInflections( )`

`resetInflections` resets the inflector's rules to their initial state, clearing out any custom rules that have been added.

Thanks to...
------------

The [Rails][rails] team for [ActiveSupport][activesupport]

The [DocumentCloud][documentcloud] team for [underscore.js][underscore]

These other Inflector implementations:

- [active-support-for-javascript](http://code.google.com/p/active-support-for-javascript/)
- [inflection-js](http://code.google.com/p/inflection-js/)
- [Javascript Rails-like inflector](http://snippets.dzone.com/posts/show/3205)

Though no code was taken directly from them, they deserve plenty of props for doing it before me. If underscore isn't your thing, check them out!

[rails]: https://github.com/rails/rails
[activesupport]: https://github.com/rails/rails/tree/master/activesupport
[underscore]: http://documentcloud.github.com/underscore/
[documentcloud]: http://www.documentcloud.org/home
