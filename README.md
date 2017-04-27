Wikibase CodeSniffer standards
==============================

Abstract
--------
This project implements a set of rules for use with [PHP CodeSniffer][0].

See [Wikibase coding conventions][1] on the MediaWiki wiki for a detailed description of the coding
conventions that are validated by these rules.

How to install
--------------
1. Create a composer.json which adds this project as a dependency:
    
    ```
    {
    	"require-dev": {
    		"wikibase/wikibase-codesniffer": "^0.2.0"
    	},
    	"scripts": {
    		"test": [
    			"phpcs -p -s"
    		],
    		"fix": "phpcbf"
    	}
    }
    ```
2. Create a phpcs.xml with our configuration:
    
    ```
    <?xml version="1.0"?>
    <ruleset>
    	<rule ref="vendor/wikibase/wikibase-codesniffer/Wikibase"/>

    	<file>.</file>
    </ruleset>
    ```
3. Install: `composer update`
4. Run: `composer test`
5. Run: `composer fix` to auto-fix some of the errors, others might need
   manual intervention.
6. Commit!

---
[0]: https://pear.php.net/package/PHP_CodeSniffer
[1]: https://www.mediawiki.org/wiki/Wikibase/Coding_conventions
