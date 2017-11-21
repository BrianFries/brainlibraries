# BrainScan Utility Library - Reference Documentation

**brainutility.lib** contains many function useful in many situations, and is recommended for use on all WebDNA pages.

All functions and global variables defined in the brainutility.lib begin with the prefix "but", short for brainutility.

### Formatting
The code style guidelines used here include the following:
- Global identifiers intended for public use begin with "but"
- Global identifiers intended for private use within the library begin with "_but"
- Local text variable names begin with a lowercase "t", followed by a camel-case descriptive name
- If the value of a text variable has been URL'ed, the variable name begins with a "u" instead of the "t"
- Local math variable names begin with "m"

Within the documentation, required function parameters are **bold**, and optional parameters are *italicised*. A parameter shown in (parentheses) is "direct" or unnamed parameter (e.g. [myFunction anUnnamedParameterValue]). In some cases a parameter may be either named or direct, with naming required if additional optional parameters are passed in.

___
## Table of Contents
<table><tr><td style="vertical-align:top;">
<a href="#butTrue">butTrue</a><br />
<a href="#butFalse">butFalse</a><br />
<a href="#butVersion">butVersion</a><br />
<a href="#butFunctions">butFunctions</a><br />
<a href="#butFunctionParam">butFunctionParam</a><br />
<a href="#butFunctionParamList">butFunctionParamList</a><br />
<a href="#butToday">butToday</a><br />
<a href="#butNow">butNow</a><br />
<a href="#butDaysToDate">butDaysToDate</a><br />
<a href="#butSecondsToTime">butSecondsToTime</a><br />
<a href="#butWeekdayOffset">butWeekdayOffset</a><br />
<a href="#butLineEnder">butLineEnder</a><br />
<a href="#butMin">butMin</a><br />
<a href="#butMax">butMax</a><br />
<a href="#butInc">butInc</a><br />
<a href="#butDec">butDec</a><br />
<a href="#butExponent">butExponent</a><br />
<a href="#butRound">butRound</a><br />
<a href="#butRandom">butRandom</a><br />
<a href="#butGetWebDNAPref">butGetWebDNAPref</a><br />
<a href="#butDefaultValue">butDefaultValue</a><br />
<a href="#butEndsWith">butEndsWith</a><br />
</td><td style="vertical-align:top;">
<a href="#butTrim">butTrim</a><br />
<a href="#butShowHTML">butShowHTML</a><br />
<a href="#butElapsedTime">butElapsedTime</a><br />
<a href="#butPassword">butPassword</a><br />
<a href="#butIsDefined">butIsDefined</a><br />
<a href="#butNotDefined">butNotDefined</a><br />
<a href="#butIsTextVar">butIsTextVar</a><br />
<a href="#butIsMathVar">butIsMathVar</a><br />
<a href="#butIsFormVar">butIsFormVar</a><br />
<a href="#butIsNumeric">butIsNumeric</a><br />
<a href="#butIsInteger">butIsInteger</a><br />
<a href="#butIsAlpha">butIsAlpha</a><br />
<a href="#butIsAlphaNumeric">butIsAlphaNumeric</a><br />
<a href="#butIsLower">butIsLower</a><br />
<a href="#butIsUpper">butIsUpper</a><br />
<a href="#butIsEmpty">butIsEmpty</a><br />
<a href="#butIsFile">butIsFile</a><br />
<a href="#butIsFolder">butIsFolder</a><br />
<a href="#butExactMatch">butExactMatch</a><br />
<a href="#butIDTagComponents">butIDTagComponents</a><br />
<a href="#butCapitalize">butCapitalize</a><br />
<a href="#butSplitMixedCaseWord">butSplitMixedCaseWord</a><br />
</td><td style="vertical-align:top;">
<a href="#butTextSet">butTextSet</a><br />
<a href="#butMathSet">butMathSet</a><br />
<a href="#butArraySet">butArraySet</a><br />
<a href="#butListToArray">butListToArray</a><br />
<a href="#butHost">butHost</a><br />
<a href="#butMIMEDate">butMIMEDate</a><br />
<a href="#butCookieExpire">butCookieExpire</a><br />
<a href="#butCookieDomain">butCookieDomain</a><br />
<a href="#butSiteRoot">butSiteRoot</a><br />
<a href="#butThisPage">butThisPage</a><br />
<a href="#butSortList">butSortList</a><br />
<a href="#butUpdateList">butUpdateList</a><br />
<a href="#butWordList">butWordList</a><br />
<a href="#butListContainsItem">butListContainsItem</a><br />
<a href="#butGetListItem">butGetListItem</a><br />
<a href="#butGetWord">butGetWord</a><br />
<a href="#butAuthorizeNet">butAuthorizeNet</a><br />
<a href="#butTCPFetch">butTCPFetch</a><br />
<a href="#butShowNonBlank">butShowNonBlank</a><br />
<a href="#butAddressFormat">butAddressFormat</a><br />
<a href="#butPhoneFormat">butPhoneFormat</a><br />
<a href="#butAge">butAge</a><br />
</td><td style="vertical-align:top;">
<a href="#butZip">butZip</a><br />
<a href="#butLoadRecord">butLoadRecord</a><br />
<a href="#butFedExLink">butFedExLink</a><br />
<a href="#butFedExTracking">butFedExTracking</a><br />
<a href="#butUPSLink">butUPSLink</a><br />
<a href="#butShippingLink">butShippingLink</a><br />
<a href="#butShortenString">butShortenString</a><br />
<a href="#butCountOccurrences">butCountOccurrences</a><br />
<a href="#butFileSize">butFileSize</a><br />
<a href="#butCSVValue">butCSVValue</a><br />
<a href="#butTextMap">butTextMap</a><br />
<a href="#butTextMapRaw">butTextMapRaw</a><br />
<a href="#butHTMLMap">butHTMLMap</a><br />
<a href="#butHTMLNoBreakMap">butHTMLNoBreakMap</a><br />
<a href="#butISO">butISO1Map</a><br />
<a href="#butUTF">butUTF8Map</a><br />
<a href="#butEntityMap">butEntityMap</a><br />
<a href="#butEditMap">butEditMap</a><br />
<a href="#butAsciiCodeMap">butAsciiCodeMap</a><br />
<a href="#butSmartMap">butSmartMap</a><br />
<a href="# VersionHistory">Version History</a><br />
</td></tr></table>

___
## <a name="butTrue">butTrue</a> and <a name="butFalse">butFalse</a>

These are global text variables defined to improve the readability of conditional expressions. They are defined as:

	[text]butTrue=1=1[/text]
	[text]butFalse=1=0[/text]

These values evaluate TRUE or FALSE in an [if], [showif] or [hideif] expression, and can be used to make code much more readable. For example, if the variable "tDoTheThing" is set to `[butTrue]` or to `[butFalse]` depending on an earlier logic decision, then you can have an expression like:

	[if [tDoTheThing]][then] (do it) [then][else] (don't do it) [/else][/if]

or

	[showif [tDoTheThing]] (do it) [/showif]

### Example
Given an email address in [tEmail], search your member.db database for that member then set a flag indicating whether a the member's status flag is set to "Active":

	[text]tActive=[butFalse][/text]
	[search db=/db/member.db&eqmemEmaildatarq=[url][tEmail][/url]][founditems]
	  [showif [memStatus]=Active][text]tActive=[butTrue][/text][/showif]
	[/founditems][/search]

Later in the page, you can then reference the tActive variable to determine what message to show the user:

	[if [tActive]][then]
	  [tEmail] is an active member.
	[/then][else]
	  [tEmail] is NOT an active member.
	[/else][/if]

### Why This Works
When WebDNA processes the "[if [tActive]]" statement, it first substitutes "[tActive]" with the stored value of the text variable named tActive, resulting in "[if 1=1]" or "[if 1=0]", depending on whether tActive was set to `[butTrue]` or `[butFalse]`. WebDNA then interprets the post-substitution statement and executes either the [then] clause or the [else] clauses.

These same values also work in the [showif], [hideif] and [switch] contexts.

___
## <a name="butVersion">butVersion</a>
This is a global text variable that indicates the version of the brainutility.lib that has been included.

___
## <a name="butFunctions">butFunctions</a>
Returns a list of the functions defined in the included brainutility.lib, each on a new line.

___
## <a name="butFunctionParam">butFunctionParam</a>
Get the value of an optional parameter to a function

### Input
- **name**	- Name of the parameter
- **params**	- The params_string from the calling function
- *default*	- Default value if not found, optional, defaults to nothing
- *trim*	- T or F (default) - Trim whitespace from value?
	
### Output
- The value of the named parameter if found, otherwise the default value

### Discussion
When writing custom functions intended for multiple use cases, there is often a great benefit to allowing for optional parameters. For example, this function itself has two optional parameters - *default* can be used to specify the values for parameters that are not passed in if something other than a blank value is desired, and *trim* provides the option to ignore leading and trailing spaces in the parameter value.

The `butFunctionParam` function provides a convenient way to implement optional parameters in your custom function.

### Example
This function tests whether the given *number* is a numeric value, and optionally requires that it is less than a *minimum* value. If no *minumum* parameter is given, it requires a minimum of zero:

	[function name=validNumber]
		[text]uParams=[url][params_string][/url][/text]
		[text]tNumber=[butFunctionParam name=number&params=[uParams]&default=MISSING&trim=T][/text]
		[text]tMinimum=[butFunctionParam name=minimum&params=[uParams]&default=0&trim=T][/text]
		[if "[math][tNumber][/math]"="[tNumber]"][then]
			[if [tNumber]<[tMinimum]][then]
				[return][butFalse][/return]
			[/then][else]
				[return][butTrue][/return]
			[/else][/if]
		[/then][else]
			[return][butFalse][/return]
		[/else][/if]
	[/function]

	[validNumber] returns [butFalse] because no `number` was passed in
	[validNumber number=13] returns [butTrue] because `number` contains a number and it's not less than the default minumum of zero<br>
	[validNumber number=-1] returns [butFalse] because `number` is less than the default minimum of zero<br>
	[validNumber number=13&minimum=10] returns [butTrue] because `number` contains a number and it's not less than the specified minimum of 10<br>
	[validNumber number=13&minimum=20] returns [butFalse] because `number` contains a number and it's  less than the specified minimum of 20<br>
	[validNumber number=-1&minimum=-10] returns [butTrue] because `number` contains a number and it's not less than the specified minimum of -10<br>

### Why This Works
There is a minimally documented system tag called `params_string` that is available inside a function, containing the full parameter string passed in to the function. So, if you call `[mufunction a=1&b=2\`, then `[params_string]` will have the value "`a=1&b=2`". The `butFunctionParam` function looks at `params_string` to see if it contains the requested parameter name, and returns it's value if found or the default value if it's not found.

___
## <a name="butFunctionParamList">butFunctionParamList</a>
Return a comma-delimited list of parameter names passed in to a function

### Input
- **(params_string)**	- The params_string from the calling function
	
### Output
- Comma-delimited list of the names of the parameters in params_string
- If no named variables but non-blank, returns, literally, "params_string"

### Discussion
This function allows for the creation of very flexible functions that can operate on any number of parameters without pre-defining the names of those parameters.

### Example:
This function will update a record in the member.db with the values passed in, adding a "mem" prefix to the field name if not provided (so you could pass in "FirstName" or "memFirstName" and both would map to the "memFirstName" field in the member.db).

	[function name=memberUpdate]
		[text]tParamList=[butFunctionParamList [params_string]][/text]
		[text]uParams=[url][params_string][/url][/text]
		[text]tMemID=[butFunctionParam name=ID&params=[uParams]&default=NO_ID][/text]
		[if "[tMemID]"="NO_ID"][then]
			[return][butFalse][/return]
		[/then][else]
			[text]tData=[/text]
			[listwords words=[tParamList]]
				[text]uValue=[url][butFunctionParam name=[word]&params=[uParams]&trim-T][/url][/text]
				[text]tData=[tData]&[hideif [word]~mem]mem[/hideif][word]=[uValue][/text]
			[/listwords]
			[replace db=/db/member.db&eqmemIDdatarq=[tMemID]]memModDate=[butToday]&memModTime=[butNow][tData][/replace]
			[return][butTrue][/return]
		[/else][/if]
	[/function]

	
___
## <a name="butToday">butToday</a>
Current date, numeric or formatted

### Input
- *DateFormat* or *direct parameter* - Date formatting string (optional, assumes math "days since 12/31/-0001" format)
- *Friendly* - T to format friendly, stripping leading zeroes from month and day numbers

### Output
- Current date, in the format specified

### Discussion
If `Friendly=T` but no `DateFormat` parameter is provided, date format defaults to WebDNA's preference setting, or `%m/%d/%Y`.

### Examples
	[butToday]<br>
	[butToday friendly=T]<br>

	Results (Executed on November 14, 2017):
	737012
	11/14/2017

___
## <a name="butNow">butNow</a>
Current time, numeric or formatted

### Input
- *TimeFormat* or *Direct Parameter* - Time formatting string (optional, assumes math "seconds since midnight" format
- *Friendly* - T to format friendly, stripping leading zeroes from Hour number
- *Lower* - T to lowercase the result, providing "am" or "pm" instead of "AM" or "PM"

### Output
- Current time, in the format specified

### Discussion
If `Friendly=T` but no `TimeFormat` parameter is provided, date format defaults to WebDNA's preference setting, or `%H:%M:%S`.

### Examples
	[butNow]<br>
	[butNow friendly=T]<br>
	[butNow timeformat=%I:%M %p]<br>
	[butNow timeformat=%I:%M %p&friendly=T&lower=T]<br>

	Results:
	59990
	16:39:50
	04:40 PM
	4:40 pm

___
## <a name="butDaysToDate">butDaysToDate</a>
Formats a Days Since value as a user-readable date

### Input
- **Days** or **direct param** - Days since 12/31/-1 as returned by [math]{[date]}[/math]
- *DateFormat* - Format to apply to the resulting date (optional, assumes WebDNA preferences format)
- Friendly - T to strip leading zeroes from day and month numbers (optional, assumes F)
	
### Output
- Formatted date

### Example
	[text]tDate=[math]{6/6/2012}[/math][/text]
	[format days_to_date %A %m/%d/%y][tDate][/format]<br>
	[butDaysToDate days=[tDate]&dateformat=%A %m/%d/%y&friendly=T]<br>
	
	Results:
	Wednesday 06/06/12
	Wednesday 6/6/12

___
## <a name="butSecondsToTime">butSecondsToTime</a>
Formats a Seconds Since Midnight value as a user-readable time

### Input
- **Seconds** or **direct param** - Seconds since Midnight as returned by [math]{[time]}[/math]
- TimeFormat - Format to apply to the resulting time (optional, assumes WebDNA preferences format)
- Friendly - T to strip leading zeroes from 12-hour numbers (optional, assumes F)
- Lower - T to surround time with lowercase for a lowercase am/pm (optional, assumes F)
	
### Output
- Formatted time

### Example
	[text]tTime=[math]{08:37:43}[/math][/text]
	[format seconds_to_time %I:%M:%S %p][tTime][/format]<br>
	[butSecondsToTime seconds=[tTime]&timeformat=%I:%M:%S %p&friendly=T&lower=T]<br>

	Results:
	08:37:43 AM
	8:37:43 am

___
## <a name="butWeekdayOffset">butWeekdayOffset</a>
Calculates a the date a specified number of weekdays (ignoring Saturday and Sunday) before or after the given date. This is useful for situations like *work will be completed in 3 business days*.

### Input
- *date* - Base date to start with - numeric or formatted (optional, assumes today's date)
- **daysbefore** or **daysafter** - Number of weekdays before or after the date to calculate

### Output
- Numeric date (Days Since 12/31/-1)

### Example
	[text]tDate=6/6/2012[/text]
	[format days_to_date %A %m/%d/%Y][butWeekdayOffset date=[tDate]&daysbefore=3][/format]<br>
	[format days_to_date %A %m/%d/%Y][math]{[tDate]}[/math][/format]<br>
	[format days_to_date %A %m/%d/%Y][butWeekdayOffset date=[tDate]&daysafter=3][/format]<br>

	Results:
	Friday 06/01/2012
	Wednesday 06/06/2012
	Monday 06/11/2012

___
## <a name="butLineEnder">butLineEnder</a>
Returns un-URL'ed %0D, %0A or %0D%0A depending on the server OS. This is particularly useful when building email messages to send with WebDNA's `[sendmail]` context.

### Input
- *System*	- UNIX, MAC or WINDOWS. If not specified, the [platform] tag is used to determine the system.
	
### Output
- UNURL'ed value of one of the following:
		%0D	on Classic Mac OS (it's an old old function)
		%0A on Unix / MacOS X
		%0D%0A on Windows

___
## <a name="butMin">butMin</a>
Returns the lesser of multiple listed values

### Input
- **ValueList** or **direct param**	- The List of values to find the minimum of
- *Alpha* - T for alphabetic minimum, F (default) for numeric
- *Delimiters*	-	Delimiters for listwords on the passed-in ValueList. If not specified, the default WebDNA word delimiters are assumed.

### Output
The minimum value from the given list

### Example
	[butMin 3,25,1400] - returns "3", the lowest numeric value
	[butMin valuelist=3,25,1400&alpha=T] - returns "1400", the lowest alphabetic value
	[butMin 17,35.2,-21] - returns "-21", the lowest numeric value
	[butMin A,C,X] - returns "0", because all values evaluate to zero as numbers
	[butMin valuelist=A,C,X&alpha=T] - returns "A", the lowest alphabetic value

___
## <a name="butMax">butMax</a>
Returns the greater of multiple listed values

### Input
- **ValueList** or **direct param**	- The List of values to find the maximum of
- *Alpha* - T for alphabetic minimum, F (default) for numeric
- *Delimiters*	-	Delimiters for listwords on the passed-in ValueList. If not specified, the default WebDNA word delimiters are assumed.

### Output
The maximum value from the given list

### Example
	[butMax 3,25,1400] - returns "1400", the greatest numeric value
	[butMax valuelist=3,25,1400&alpha=T] - returns "3", the greatest alphabetic value
	[butMax 17,35.2,-21] - returns "35", the greatest numeric value
	[butMax A,C,X] - returns "0", because all values evaluate to zero as numbers
	[butMax valuelist=A,C,X&alpha=T] - returns "X", the greatest alphabetic value

___
## <a name="butInc">butInc</a>
Increment a global variable by a specified amount.

### Input
- **TextVar** or **MathVar** or **direct param** - The name of a global variable to increment. If using a direct param, it is assumed to be a text variable.
- *By* - Amount to increment the variable by, assumes 1 if not specified

## Output:
- none, or an error message
- If no errors, the specified global variable will be updated

## Discussion
In certain situations, using this function is more clear to read than using the equivalent WebDNA math code, particularly when storing values in text variables.

## Example
	[butInc tCount] - Increments the global text variable "tCount" by 1
	Equivalent to: [text]tCount=[math][tCount]+1[/math][/text]
	[butInc MathVar=mCount&by=10] - Increments the global math variable "mCount" by 10
	Equivalent to: [math show=F]mCount=mCount+10[/math]
___
## <a name="butDec">butDec</a>
Decrement a global variable by a specified amount

### Input
- **TextVar** or **MathVar** or **direct param** - The name of a global variable to decrement. If using a direct param, it is assumed to be a text variable.
- *By* - Amount to decrement the variable by, assumes 1 if not specified

## Output:
- none, or an error message
- If no errors, the specified global variable will be updated

## Discussion
In certain situations, using this function is more clear to read than using the equivalent WebDNA math code, particularly when storing values in text variables.

## Example
	[butDec tCount] - Decrements the global text variable "tCount" by 1
	Equivalent to: [text]tCount=[math][tCount]-1[/math][/text]
	[butDec MathVar=mCount&by=10] - Decrements the global math variable "mCount" by 10
	Equivalent to: [math show=F]mCount=mCount-10[/math]

___
## <a name="butExponent">butExponent</a>
Raise value to a given power.

### Input
- *value* - The number to be raised, default 10
- *power* - power to raise the value to, default 1, supports positive and negative exponents

### Output
- the number, raised exponentially

### Example
	[butExponent value=2&power=3] - returns 8 (2^3)
	[butExponent value=2&power=0] - returns 1 (2^0)
	[butExponent value=2&power=-2] - returns 0.25 (2^-2)
	[butExponent power=3] - returns 1000 (10^3)

___
## <a name="butRound">butRound</a>
Round a number off to the given precision

### Input
- **value** or **direct param**	- The number to be rounded
- *precision* - Number of decimal places to round to, default 0. Use negative number for zeros to left of decimal.

### Output
- the number, rounded

### Example
	[butRound 1234.67] - returns 1235
	[butRound value=1234.67&precision=1] - returns 1234.7
	[butRound value=1234.67&precision=-2] - returns 1200

___
## <a name="butRandom">butRandom</a>
Random number with easier controls than WebDNA's built in `[random]` tag

### Input
- *min* - The minimum allowed value (default 0)
- *max* - The maximum allowed value (default 99 for integer, 1.0 for float)
- *type* - I or Integer (default), F or Float

### Output
- a random number within the specified range

### Example
	[butRandom min=5&max=50]		- Generates random integer from 5 to 50
	[butRandom min=1&max=2&type=F]	- Generates random floating point number from 1.0000 to 2.0000
___
## <a name="butGetWebDNAPref">butGetWebDNAPref</a>
Get the value of a WebDNA preference field

### Input
- **key** or **direct param** - the preference key to lookup
- *default* - optional value if the preference is not found, assumes blank

### Output
- value of the specified key
 
### Discussion
These are the values set in WebDNA's preferences template. 
Some that may be useful include:

AutoCommit - "T" if databases are set to automatically write to disk after each change
DateFormat - default format returned by the [date] tag
TimeFormat - default format used by the [time] tag
UnixUser - name of the Unix user used by WebDNA
ValidDatabaseExtensions - list of file name extensions that may be used for database
ValidTemplateExtensions - list of file name extensions that may be served to clients via WebDNA

To see a list of all available preference values, run this code:
	[search db=WebCatalog Prefs&nepreferencedatarq=X&allhit=1&preferencesort=1][founditems][preference]: [value]<br>[/founditems][/search]

If "WebCatalog Prefs" gives a DBError, this function will check in "webdna.ini", so it supports both Server and FastCGI versions of WebDNA.

### Example
	[butGetWebDNAPref DateFormat] - returns the value of the DateFormat preference ("%m/%d/%Y" for U.S. systems)

___
## <a name="butDefaultValue">butDefaultValue</a>
Returns given value if it is not blank, or the given default value if it is.

### Input
- **value** - the value to return
- **default** - the default value to return if `value` is blank

### Output
- either the `value` or the `default`

### Discussion
This can be useful to display a default value when a field in a database may be blank.

### Example
	[search db=/db/member.db&eqmemIDdatarq=1][founditems]
		The member's email address is [butDefaultValue value=[url][memEmail][/url]&default=(not specified)]
	[/founditems][/search]
	
	If the memEmail in the database is set to "me@example.com", this will return:
		The member's email address is me@example.com
	
	If the memEmail in the database is blank, this will return:
		The member's email address is (not specified)

___
## <a name="butEndsWith">butEndsWith</a>
Tests whether the given string ends with the given characters. WebDNA has a built-in "begins with" operator - `[showif [mystring]~Bob]` will test whether the `mystring` variable begins with "Bob" - but no equivalent "Ends With" operator.

### Input
- **string** - the string to test
- **find** - the text to look for at the end of the `string`

### Output
- `[butTrue]` or `[butFalse]`

### Example
	[if [butEndsWith string=[filename]&find=.txt]][then]
		Yes, this is a text file
	[/then][else]
		Not, this is not a text file
	[/else][/if]

___
## <a name="butTrim">butTrim</a>
Strip returns and leading tabs and spaces from each line passed in, useful for making `[replace]` or `[append]` parameters more readable.

### Input
- **(direct param)** - the text to trim

### Output
- Trimmed version of the text

### Discussion
Given a situation where you want to update multiple fields in a database record, the data string for a `[replace]` or `[append]` context can quickly get unwieldy and difficult to read. The `[butTrim]` function provides a way to improve the readability of your code.

Given an append context like this:

	[append db=/db/member.db]memFirstName=Brian&memLastName=Fries&memEmailAddress=brian.fries@example.com&memAddress=1313 Mockingbird Lane[/append]

Some developers may choose to put each field on a separate line and use comments to eliminate white space:

	[append db=/db/member.db][!]
		[/!]memFirstName=Herman[!]
		[/!]&memLastName=Munster[!]
		[/!]&memEmailAddress=herman.munster@example.com[!]
		[/!]&memAddress=1313 Mockingbird Lane[!]
	[/!][/append]

Using `[butTrim]` makes this code cleaner and easier to read, as shown in the Example below. It uses `[grep]` to remove line enders and leading spaces and tabs from the string that is passed in.

### Example

	[append db=/db/member.db][butTrim [url]
		memFirstName=Herman
		&memLastName=Munster
		&memEmailAddress=herman.munster@example.com
		&memAddress=1313 Mockingbird Lane
	[/url]][/append]

___
## <a name="butShowHTML">butShowHTML</a>
Maps < to &amp;lt; and > to &amp;gt; so HTML is visible instead of interpreted

### Input
- **(direct param)** - the HTML code

### Output
- The passed-in code, mapped so the HTML is displayed by rather than interpreted by the browser

### Example
	[text]tSampleCode=<b>Bold Text</b>[/text]
	Here is the sample code:
	[butShowHTML [tSampleCode]]
	
	Results (as displayed in the browser):
	Here is the sample code:
	<b>Bold Text</b>

___
## <a name="butElapsedTime">butElapsedTime</a>
Convert WebDNA's `[elapsedtime]` value, which returns an integer number of "ticks", which are 1/60 of a second, into readable time, with hours, minutes, seconds, and hundredths of a second.

### Input
- *Elapsed* or *direct param* - an `[elapsedtime]` value, defaults to the current value of `[elapsedtime]`
- *TicksPerSecond* - The number of ticks per second, defaults to 60, but can be set to a different value if necessary

### Output
- The elapsed time in hours, minutes, seconds and fractions thereof (decimal).

### Discussion
 Keep in mind this is still restricted to the 1/60th of a second precision of `[elapsedtime]`, but it is more human-readable.

`[butElapsedTime]` is very useful for debugging performance issues on a web page that is taking a long time to load. By adding `[butElapsedTime]` in HTML comment tags at key points in the page, you can load the page and view the source in your browser, looking for the elapsed time values to determine where the processing time is being spent.

### Example
	[text]tBefore=[butElapsedTime][/text]
	[search db=...]
		[founditems]
			...
		[/founditems]
	[/search]
	Execution time for the above search block: [math][butElapsedTime]-[tBefore][/math]
	
	Results, if the code took 4000 ticks to execute (a little over a minute):
	(...search results...)
	Execution time for the above search block: 1:06.67
	
___
## <a name="butPassword">butPassword</a>
Returns an algorithmically generated password, helpful for automatically assigning passwords to new users.

### Input
- *Length* - Number of characters (optional, assumes 8)
- *Layout* - Layout of password (optional), where:
	- X = any letter, upper or lower case
	- U = uppercase letter
	- L = lowercase letter
	- V = lowercase vowel, a, e, i, o or u
	- 9 = numeric digit
	- \# = special character
	- \* = any character
- *AlphaCase* - Case of alpha characters - MIXED, UPPER or LOWER (optional, assumes LOWER)
- *Special* - List of possible special characters (optional, assumes "!@#$%&*:;?")
	
### Output:
- A randomly generated password as specified

### Discussion
If a Layout is provided, then Length and AlphaCase will be ignored, and a password will be generated with the format specified by the layout. For example, "UL99#99X" would generate a password with an uppercase letter, a lowercase letter, two digits, a special character, two more digits, and two letters of either case, creating a password such as "Vy86@67a".

Lowercase L, uppercase I and O, and the digits 1 an 0 are not included because of possible user confusion from similar looking characters.

### Example
	[butPassword length=12&AlphaCase=Mixed&special=___---]
	[butPassword layout=XX99#99X&AlphaCase=Mixed]

	Sample Results:
	4_3y9v3-ZQM8
	fk72@36X

___
## <a name="butIsDefined">butIsDefined</a>
Returns `[butTrue]` if given name is a defined tag or variable, else `[butFalse]`

### Input
- **direct param** - Name of item to test

### Output
- `[butTrue]` if variable is defined, else `[butFalse]`
- Global variable `[butValue]` is set to the value of the variable if it is defined

### Discussion
This is most useful when you have a number of variables that may or may not have been defined elsewhere, and you wish to display or utilize their values if they are defined.

The key statement in this function is this:
- `[text]tValue=[interpret][[params_string]][/interpret][/text]`

If `[tValue]` then begins and ends with square brackets, it is considered to be defined and will return `[butTrue]`. Note that this can result in false positives if, for example, you have this:
```
[text]myVariable=[bracketed content][/text]
[butIsDefined myVariable]
```

*Warning*:
The parameter passed in will be interpreted as WebDNA code to determine whether it is defined. Thus, if you pass in "deletefile filename" then file "filename" will be deleted if it exists!

### Example
	[text]myVariable=Monkey[/text]
	[listwords words=myVariable,myOtherVariable]
	[if [butIsDefined [word]]][then]
		[word] is defined and it's value is "[butValue]"<br>
	[/then][else]
		[word] is not defined<br>
	[/else][/if]

	Results:
	myVariable is defined and it's value is "Monkey"
	myOtherVariable is not defined

___
## <a name="butNotDefined">butNotDefined</a>
Returns `[butTrue]` if given name is NOT a defined tag or variable, else `[butFalse]`

### Input
- **direct param** - Name of item to test

### Output
- `[butTrue]` if variable is NOT defined, else `[butFalse]`
- Global variable `[butValue]` is set to the value of the variable if it is defined

### Discussion
This is the reverse of *<a href="#butIsDefined">[butIsDefined]</a>*, and it carries the same caveats as that function. The purpose of this function is to make code more readable if you would prefer a positive result when a variable has not been defined.

### Example
	[text]myVariable=Monkey[/text]
	[listwords words=myVariable,myOtherVariable]
	[if [butNotDefined [word]]][then]
		[word] is not defined<br>
	[/then][else]
		[word] is defined and it's value is "[butValue]"<br>
	[/else][/if]

	Results:
	myVariable is defined and it's value is "Monkey"
	myOtherVariable is not defined

___
## <a name="butIsTextVar">butIsTextVar</a>
Returns `[butTrue]` if given name is a defined text variable, else `[butFalse]`

### Input
- **Name** or **direct param** - Name of the text variable to look for
- *Scope* - Scope to look in (optional, defaults to global scope)

### Output
- `[butTrue]` if the given name is a defined text variable in the specified scope, else `[butFalse]`
- Global variable `[butValue]` is set to the value of the variable if it is defined

### Discussion
Unlike *<a href="#butIsDefined">[butIsDefined]</a>*, this function uses the `[listvariables]` context to determine whether the variable is defined or not, so it is not subject to the false-positive or code-execution issues that `[butIsDefined]` is.

`Scope` is an important consideration for this function. If you are calling `[butIsTextVar]` from inside a function, it will still only look in the global scope, unless you specify the local scope, which is the same as the name of the function the variable is defined in. See the Example below for clarification.

### Examples
	[text]aGlobal=hello[/text]
	[text]dupName=global[/text]
	[function name=myFunction]
		[text]aLocal=greetings[/text]
		[text]dupName=local[/text]
		[listwords words=aGlobal,aLocal,dupName]
			[text]tVarName=[word][/text]
			[listwords words=_,global,myFunction]
				[text]tScope=[word][/text]
				[if "[tScope]"="_"][then]
					[if [butIsTextVar [tVarName]]][then]
						[tVarName] has value "[butValue]"<br>
					[/then][else]
						[tVarName] is not defined<br>
					[/else][/if]
				[/then][else]
					[if [butIsTextVar name=[tVarName]&scope=[tScope]]][then]
						[tVarName] in scope "[tScope]" has value "[butValue]"<br>
					[/then][else]
						[tVarName] is not defined in scope "[tScope]"<br>
					[/else][/if]
				[/else][/if]
			[/listwords]
			<br>
		[/listwords]
	[/function]
	[myFunction]
	
	Results:
	aGlobal has value "hello"
	aGlobal in scope "global" has value "hello"
	aGlobal is not defined in scope "myFunction"

	aLocal is not defined
	aLocal is not defined in scope "global"
	aLocal in scope "myFunction" has value "greetings"

	dupName has value "global"
	dupName in scope "global" has value "global"
	dupName in scope "myFunction" has value "local"


___
## <a name="butIsMathVar">butIsMathVar</a>
Returns `[butTrue]` if given name is a defined math variable, else `[butFalse]`

### Input
- **Name** or **direct param** - Name of the math variable to look for
- *Scope* - Scope to look in (optional, defaults to global scope)

### Output
- `[butTrue]` if the given name is a defined text variable in the specified scope, else `[butFalse]`
- Global variable `[butValue]` is set to the value of the variable if it is defined

### Discussion
Unlike *<a href="#butIsDefined">[butIsDefined]</a>*, this function uses the `[listvariables]` context to determine whether the variable is defined or not, so it is not subject to the false-positive or code-execution issues that `[butIsDefined]` is.

`Scope` is an important consideration for this function. If you are calling `[butIsMathVar]` from inside a function, it will still only look in the global scope, unless you specify the local scope, which is the same as the name of the function the variable is defined in. See the Example below for clarification.

### Examples
	[math show=F]aGlobal=100[/math]
	[math show=F]dupName=110[/math]
	[function name=myFunction]
		[math show=F]aLocal=200[/math]
		[math show=F]dupName=210[/math]
		[listwords words=aGlobal,aLocal,dupName]
			[text]tVarName=[word][/text]
			[listwords words=_,global,myFunction]
				[text]tScope=[word][/text]
				[if "[tScope]"="_"][then]
					[if [butIsMathVar [tVarName]]][then]
						[tVarName] has value "[butValue]"<br>
					[/then][else]
						[tVarName] is not defined<br>
					[/else][/if]
				[/then][else]
					[if [butIsMathVar name=[tVarName]&scope=[tScope]]][then]
						[tVarName] in scope "[tScope]" has value "[butValue]"<br>
					[/then][else]
						[tVarName] is not defined in scope "[tScope]"<br>
					[/else][/if]
				[/else][/if]
			[/listwords]
			<br>
		[/listwords]
	[/function]
	[myFunction]
	
	Results:
	aGlobal has value "100"
	aGlobal in scope "global" has value "100"
	aGlobal is not defined in scope "myFunction"

	aLocal is not defined
	aLocal is not defined in scope "global"
	aLocal in scope "myFunction" has value "200"

	dupName has value "110"
	dupName in scope "global" has value "110"
	dupName in scope "myFunction" has value "210"

___
## <a name="butIsFormVar">butIsFormVar</a>
Returns `[butTrue]` if given name is a defined form variable, else `[butFalse]`

### Input
- **Name** or **direct param** - Name of the form variable to look for

### Output
- `[butTrue]` if the given name is a defined form variable, else `[butFalse]`
- Global variable `[butValue]` is set to the value of the variable if it is defined

### Discussion
Unlike *<a href="#butIsDefined">[butIsDefined]</a>*, this function uses the `[formvariables]` context to determine whether the variable is defined or not, so it is not subject to the false-positive or code-execution issues that `[butIsDefined]` is.

### Examples
	[text]tMyValue=[if [butIsFormVar myValue]][then][butValue][/then][else](default value)[/else][/if][/text]

	Results:
	If a form variable named "myValue" was passed in to the page, then text variable `[tMyValue]` will be set to the value of the formvariable. Otherwise, it will be set to "(default value)"

___
## <a name="butIsNumeric">butIsNumeric</a>
Returns `[butTrue]` if given value is numeric, else `[butFalse]`
Allows digits (0-9), one decimal point and a leading minus sign

### Input
- **Number** or **direct parameter**	-	Value to test for numeric
- *Decimal* - Decimal separator character, should be "." or "," depending upon your locality (optional, defaults to ".")

### Output
- `[butTrue]` if numeric, else `[butFalse]`

### Examples
	[text]tNum=123.45[/text]
	[text]tNotNum=123 and 45[/text]
	[tNum] [if [butIsNumeric [tNum]]][then]is[/then][else]is not[/else][/if] a number.<br>
	[tNotNum] [if [butIsNumeric [tNotNum]]][then]is[/then][else]is not[/else][/if] a number.<br>

	Results:
	123.45 is a number.
	123 and 45 is not a number.

___
## <a name="butIsInteger">butIsInteger</a>
Returns `[butTrue]` if given value is an integer, else `[butFalse]`
Allows only digits (0-9) and a leading minus sign
Optional value range tests

### Input
- **Number** or **direct parameter**	-	Value to test for integer
- *Min* - Minimum acceptable value (optional, defaults to no minimum value)
- *Max* - Maximum acceptable value (optional, defaults to no maximum value)

### Output
	`[butTrue]` if integer and passes optional range testing, else `[butFalse]`

### Examples
	[text]tInt=123[/text]
	[text]tNotInt=123.45[/text]
	[tInt] [if [butIsInteger [tInt]]][then]is[/then][else]is not[/else][/if] an integer.<br>
	[tNotInt] [if [butIsInteger [tNotInt]]][then]is[/then][else]is not[/else][/if] an integer.<br>
	[tInt] [if [butIsInteger number=[tInt]&min=1&max=100]][then]is[/then][else]is not[/else][/if] an integer in range 1-100.<br>

	Results:
	123 is an integer.
	123.45 is not an integer.
	123 is not an integer in range 1-100.
___
## <a name="butIsAlpha">butIsAlpha</a>
Returns `[butTrue]` if given value is an all alphabetic characters, else `[butFalse]`
Allows only low-ASCII characters (a-z, A-Z)

### Input
- **Value** or **direct parameter**	-	Value to test for Alphabetic

### Output
	`[butTrue]` if all low-ASCII alphabetic characters

### Examples
	[text]tAlpha=Abc[/text]
	[text]tNotAlpha=Abc Def[/text]
	[text]tAlphaNum=Abc123[/text]
	[tAlpha] [if [butIsAlpha [tAlpha]]][then]is[/then][else]is not[/else][/if] all alphabetical.<br>
	[tNotAlpha] [if [butIsAlpha [tNotAlpha]]][then]is[/then][else]is not[/else][/if] all alphabetical.<br>
	[tAlphaNum] [if [butIsAlpha [tAlphaNum]]][then]is[/then][else]is not[/else][/if] all alphabetical.<br>

	Results:
	123 is an integer.
	123.45 is not an integer.
	123 is not an integer in range 1-100.
___
## <a name="butIsAlphaNumeric">butIsAlphaNumeric</a>
Returns `[butTrue]` if given value is all alphabetic characters and digits, else `[butFalse]`
Allows only low-ASCII characters (a-z, A-Z) and digits (0-9)

### Input
- **Value** or **direct parameter**	-	Value to test for AlphaNumeric

### Output
	`[butTrue]` if low-ASCII alphabetic characters or digits, else `[butFalse]`

### Examples
	[text]tAlpha=Abc[/text]
	[text]tNotAlpha=Abc Def[/text]
	[text]tAlphaNum=Abc123[/text]
	[tAlpha] [if [butIsAlpha [tAlpha]]][then]is[/then][else]is not[/else][/if] all alphabetical.<br>
	[tNotAlpha] [if [butIsAlpha [tNotAlpha]]][then]is[/then][else]is not[/else][/if] all alphabetical.<br>
	[tAlphaNum] [if [butIsAlpha [tAlphaNum]]][then]is[/then][else]is not[/else][/if] all alphabetical.<br>

	Results:
	123 is an integer.
	123.45 is not an integer.
	123 is not an integer in range 1-100.

___
## <a name="butIsLower">butIsLower</a>
Returns `[butTrue]` if given value contains no upper-case characters

### Input
- **Value** or **direct parameter**	- Value to test

### Output
- `[butTrue]` if lowercase, else `[butFalse]`

### Discussion
This can be used to make case-sensitive comparisons, which WebDNA does not support natively. The test is done by comparing `[encrypt][value][/encrypt]` to `[encrypt][lowercase][value][/lowercase][/encrypt]`, as `[encrypt]` will return a different value for an uppercase "A" than for a lowercase "a".

*Note* this only works reliably for standard ASCII characters, and does not account for Unicode characters.

### Examples
	[text]tLower=this is some text[/text]
	[text]tMixed=This is some TEXT[/text]
	[text]tUpper=THIS IS SOME TEXT[/text]
	[tLower]: [hideif [butIsLower [tLower]]]NOT[/hideif] lowercase<br>
	[tMixed]: [hideif [butIsLower [tMixed]]]NOT[/hideif] lowercase<br>
	[tUpper]: [hideif [butIsLower [tUpper]]]NOT[/hideif] lowercase<br>

	Results:
	this is some text: lowercase
	This is some TEXT: NOT lowercase
	THIS IS SOME TEXT: NOT lowercase

___
## <a name="butIsUpper">butIsUpper</a>
Returns `[butTrue]` if given value contains no lower-case characters

### Input
- **Value** or **direct parameter**	- Value to test

### Output
- `[butTrue]` if lowercase, else `[butFalse]`

### Discussion
This can be used to make case-sensitive comparisons, which WebDNA does not support natively. The test is done by comparing `[encrypt][value][/encrypt]` to `[encrypt][uppercase][value][/uppercase][/encrypt]`, as `[encrypt]` will return a different value for an uppercase "A" than for a lowercase "a".

*Note* this only works reliably for standard ASCII characters, and does not account for Unicode characters.

### Examples
	[text]tLower=this is some text[/text]
	[text]tMixed=This is some TEXT[/text]
	[text]tUpper=THIS IS SOME TEXT[/text]
	[tLower]: [hideif [butIsLower [tLower]]]NOT[/hideif] lowercase<br>
	[tMixed]: [hideif [butIsLower [tMixed]]]NOT[/hideif] lowercase<br>
	[tUpper]: [hideif [butIsLower [tUpper]]]NOT[/hideif] lowercase<br>

	Results:
	this is some text: NOT uppercase
	This is some TEXT: NOT uppercase
	THIS IS SOME TEXT: uppercase

___
## <a name="butIsEmpty">butIsEmpty</a>
Returns `[butTrue]` if given variable name has blank value, else `[butFalse]`

### Input
- **var** or **direct parameter** - Name of the variable to test

### Output
- `[butTrue]` if the named variable is empty, else `[butFalse]`

### Discussion
This takes a VARIABLE NAME as a parameter, not a value.

### Examples
	[text]tEmpty=[/text]
	[text]tNotEmpty=abc[/text]
	tEmpty is [hideif [butIsEmpty tEmpty]]NOT[/hideif] empty<br>
	tNotEmpty is [hideif [butIsEmpty tNotEmpty]]NOT[/hideif] empty<br>

___
## <a name="butIsFile">butIsFile</a>
Returns `[butTrue]` if given path represents an existing file, else `[butFalse]`

### Input
- **path** or **direct parameter** - Path to the file to check for

### Output
- `[butTrue]` if the path refers to an existing file, else `[butFalse]`

### Examples
	[text]tPath=testfile.txt[/text]
	[writefile [tPath]]contents[/writefile]
	Wrote: [tPath] is [hideif [butIsFile [tPath]]]NOT[/hideif] a FILE<br>
	[deletefile [tPath]]
	Deleted: [tPath] is [hideif [butIsFile [tPath]]]NOT[/hideif] a FILE<br>
	[createfolder [tPath]]
	Folder: [tPath] is [hideif [butIsFile [tPath]]]NOT[/hideif] a FILE<br>
	[deletefolder [tPath]]
	Deleted: [tPath] is [hideif [butIsFile [tPath]]]NOT[/hideif] a FILE<br>
	
	Results:	
	Wrote: testfile.txt is a FILE
	Deleted: testfile.txt is NOT a FILE
	Folder: testfile.txt is NOT a FILE
	Deleted: testfile.txt is NOT a FILE

___
## <a name="butIsFolder">butIsFolder</a>
Returns `[butTrue]` if given path represents an existing folder, else `[butFalse]`

### Input
- **path** or **direct parameter** - Path to the folder to check for

### Output
- `[butTrue]` if the path refers to an existing folder, else `[butFalse]`

### Examples
	[text]tPath=testfolder[/text]
	[writefile [tPath]]contents[/writefile]
	Wrote: [tPath] is [hideif [butIsFolder [tPath]]]NOT[/hideif] a FOLDER<br>
	[deletefile [tPath]]
	Deleted: [tPath] is [hideif [butIsFolder [tPath]]]NOT[/hideif] a FOLDER<br>
	[createfolder [tPath]]
	Folder: [tPath] is [hideif [butIsFolder [tPath]]]NOT[/hideif] a FOLDER<br>
	[deletefolder [tPath]]
	Deleted: [tPath] is [hideif [butIsFolder [tPath]]]NOT[/hideif] a FOLDER<br>
	
	Results:	
	Wrote: testfolder is NOT a FOLDER
	Deleted: testfolder is NOT a FOLDER
	Folder: testfolder is a FOLDER
	Deleted: testfolder is NOT a FOLDER

___
## <a name="butExactMatch">butExactMatch</a>
Returns `[butTrue]` if values pass case-sensitive comparison

### Input
- **Value1** - The first value to test
- **Value2** - The value to compare to Value1

### Output
- `[butTrue]` if the values match a case-sensitive comparison, else `[butFalse]`

### Discussion
Unlike WebDNA's standard text comparisons, this function compares text on a case-sensitive basis, so "Herman" does not match "herman". This is done by comparing `[encrypt][Value1][/encrypt]` to `[encrypt][Value2][/encrypt]`, as `[encrypt]` will return a different value for an uppercase "A" than for a lowercase "a".

*Note* this only works reliably for standard ASCII characters, and does not account for Unicode characters.

### Examples
	[text]t1=George Jetson[/text]
	[text]t2=george jetson[/text]
	[if "[t1]"="[t2]"][then]
		[if [butExactMatch value1=[t1]&value2=[t2]]][then]
			"[t1]" exactly matches "[t2]"
		[/then][else]
			"[t1]" and "[t2]" differ only in capitalization
		[/else][/if]
	[/then][else]
		"[t1]" does not match "[t2]"
	[/else][/if]

	Results:
	"George Jetson" and "george jetson" differ only in capitalization
	
___
## <a name="butIDTagComponents">butIDTagComponents</a>
Break an ID tag value (such as "ABC123X") into prefix, number and suffix

### Input
- **Value** or **direct parameter - tag to be parsed

### Output
- `[butTrue]` if a number was found within the tag, else `[butFalse]`
- Global variable `[butPrefix]` is set to the portion of the tag before the number
- Global variable `[butNumber]` is set to the numeric portion of the tag
- Global variable `[butSuffix]` is set to the portion of the tag following the number

### Discussion
Given an existing ID tag value, such as an asset tag from a company-owned computer, this function can be used in programmatically calculating the next ID tag in the sequence. See the example below for clarification.

### Examples
	[text]tOldTag=XYZ001234-PC[/text]
	[if [butIDTagComponents [tOldTag]]][then]
		[!] Increment numeric component and pad with leading zeroes [/!]
		[text]tLength=[countchars][butNumber][/countchars][/text]
		[text]tNewNumber=[format .[tLength]d][math][butNumber]+1[/math][/format][/text]
		The Numeric portion is incremented from [butNumber] to [tNewNumber]<br>
		[!]Add prefix and suffix[/!]
		[text]tNewTag=[butPrefix][tNewNumber][butSuffix][/text]
		The tag after "[tOldTag]" is "[tNewTag]"
	[/then][else]
		"[tOldTag]" is not a valid ID tag.
	[/else][/if]

	Results:
	The Numeric portion is incremented from 001234 to 001235
	The tag after "XYZ001234-PC" is "XYZ001235-PC"

___
## <a name="butCapitalize">butCapitalize</a>
Capitalize text, but only if given text is all uppercase or all lowercase

### Input
- **Value** or **direct parameter** - Text to be capitalized

### Output
- If the Value contains both uppercase and lowercase letters, it is returned unchanged
- Otherwise, returns the Capitalized Version Of The Text

### Discussion
If the text passed in contains mixed case, such as "Sally McIntyre", it will be returned unchanged. This makes it safer to use on data entered by a user, so text like "I work for IBM" doesn't get changed to "I work for Ibm".

### Examples
	[butCapitalize my father is herman munster.]<br>
	[butCapitalize I LOVE LAMP.]<br>
	[butCapitalize John O'Brien uses SQL.]<br>

	Results:
	My Father is Herman Munster.
	I Love Lamp.
	John O'Brien uses SQL.
	
___
## <a name="butSplitMixedCaseWord">butSplitMixedCaseWord</a>
Break up mixed case word into separate capitalized words

### Input
- **Value** or **direct parameter** - Text to be split

### Output
- Text split up as separate words

### Discussion
This is a convenient way to quickly display variable or field names in a more human-friendly way. If your database has field names like "orderDate", "orderSubTotal" and "orderGrandTotal", running those names through butSplitMixedCaseWord would display them as "Order Date", "Order Sub Total" and "Grand Total".

### Examples
	[listwords words=orderDate,orderSubTotal,orderGrandTotal]
		[text][word]=value [index][/text]
		[butSplitMixedCaseWord [word]] = [interpret][[word]][/interpret]<br>
	[/listwords]

	Results:
	Order Date = value 1
	Order Sub Total = value 2
	Order Grand Total = value 3

___
## <a name="butTextSet">butTextSet</a>
Set a global text variable

### Input
- **direct parameter** - Assignment statement

### Output
- *none*
- the assignment statement (if valid) will set a global text variable

### Discussion
Not a lot of point to this, except to slightly simplify the syntax by letting you say `[butTextSet a=Monkey]` instead of `[text]a=Monkey[/text]`. This is largely here as a complement to `[butMathSet]` for consistency.

### Examples
	[text]a=Monkey[/text]
	[butSetText b=Chimp]
	a=[a]<br>
	b=[b]<br>
	
	Results:
	a=Monkey
	b=Chimp
	
___
## <a name="butMathSet">butMathSet</a>
Set a global **text** variable with a math expression

### Input
- **direct parameter** - Assignment statement

### Output
- *none*
- the assignment statement (if valid) will set a global text variable

### Discussion
Brief history... In the early days of WebDNA, there were no text variables, only math variables. Math variables have been left unchanged, but the newer text variables have several advantages. First, the default of the "show" parameter is "F" for text variables, while it is "T" for math variables. In the early days that made sense, as math was mostly for performing calculations, which you probably wanted to show on the page, vs. setting variables, which you probably don't want to show at the moment, but use later on in the code. Second, math variable name are limited to 15 characters

### Examples

	Results:
	
___
## <a name="butArraySet">butArraySet</a>
Set an indexed array value

### Input
- **direct parameter** - Assignment statement, such as "arrayname(x,y)=value"
	*Note*: Array "arrayname" must be defined and "(x,y)" must be valid indices for the array

### Output
- *none*, or an error message if there is a problem

### Discussion
WebDNA arrays are awkward to use, and I don't use them. Ever. I tried when they were new, but they did not serve the need I was looking for, and I use other techniques instead, such as storing a series of values in a comma-delimited text variable and using `[listwords]` to extract values.

During my experimentation with arrays, I did create and keep this function to simplify the syntax of setting the value for a particular index in an array. See the example below for clarification.

*Note* this works only on global-scope arrays.

### Examples
	[arrayset name=aDays&dim=7](1)=Sun&(2)=Mon&(3)=Tue&(4)=Wed&(5)=Thu&(6)=Fri&(7)=Sat[/arrayset]
	[!] WebDNA syntax to update the value at index 2: [/!]
	[arraySet name=aDays](2)=Turtle[/arraySet]
	[!] BrainUtility syntax to update the value at index 3: [/!]
	[butArraySet aDays(3)=Frog]
	[!] Dump the contents of the array: [/!]
	[loop start=1&end=7][aDays([index])]<br>[/loop]

	Results:
	Sun
	Turtle
	Frog
	Wed
	Thu
	Fri
	Sat

___
## <a name="butListToArray">butListToArray</a>
Returns contents of list formatted for populating an array

### Input
- **List** - delimited list of values
- *Delimiters* - character(s) separating values in List (optional, default ",")
- *Max* - maximum number of values to use (optional, use if list may exceed dim of array)
	
### Output
- Values from the list formatted for use in `[arrayset]`
	
### Discussion
Another remnant from my dalliance with WebDNA Arrays, this will conveniently take a list of values as you may use in `[listwords]` and format them for setting values in an `[arrayset]` context.

### Examples
	[text]tList=bob,carol,ted,alice,ross&rachel[/text]
	[arrayset name=aSet&dim=20][butListToArray list=[url][tList][/url]&delimiters=[url],&[/url]][/arrayset]
	[loop start=1&end=6][index]:[aSet([index])]<br>[/loop]

	Results:
	1:bob
	2:carol
	3:ted
	4:alice
	5:ross
	6:rachel

___
## <a name="butHost">butHost</a>
Returns the host name, extracted from MIME headers

### Input
- *none*

### Output
- Host name

### Discussion
This function will first look for a MIME header named "HTTP_HOST". Failing that, it will find the first MIME header whose name contains "host".

If the reported host name includes "http:" or "https:", that portion will be stripped from the returned value.

### Examples
	[butHost]

	Results:
	www.brainscansoftware.com
	
___
## <a name="butMIMEDate">butMIMEDate</a>
Returns MIME-compatible date, calculated with offsets from current date/time

### Input
- *GMTOffset* - Hours offset from GMT to local time (optional, assumes server's GMT offset)
- *years* - Years from now to expire cookie (optional)
- *months* - Months from now to expire cookie (optional)
- *days* - Days from now to expire cookie (optional)
- *hours* - Hours from now to expire cookie (optional)
- *minutes* - Minutes from now to expire cookie (optional)
- *seconds* - Seconds from now to expire cookie (optional)
- *expiredate* - Specific date to expire cookie on, formatted or days-since (optional)
- *expiretime* - Specific time of day to expire cookie, formatted or minutes-since (optional)
- *fullday* - T to show full day name (Tuesday instead of Tue)
	
### Output
- MIME-formatted date and time string
- Format example: Wed, 09 Nov 1999 23:12:40 GMT

### Discussion
This function will format a date and time string that meets the RFC for MIME values. By default, it will provide the current date and time, using the GMT Offset set on the server (*note*: does not support automatic GMT Offset detection on Windows servers).

Optionally, you may specify an amount of time into the future to calculate the date string for (using the `years`, `days`, `minutes`, etc., parameters), or specify a particular date and time to calculate the date string for (using the `expiredate` and `expiretime` parameters).

The WebDNA documentation for the `[setcookie]` tag states that the day of the week must be specified in full, such as "Friday" instead of "Fri" as specified in the RFC. My testing has indicated that the shortened version of the day name works in `[setcookie]`, but the `fullday` parameter exists to allow the programmer to choose which format to use (see also `butCookieExpire` below).

### Examples
	[butMIMEDate]<br>
	[butMIMEDate days=1&hours=2]<br>
	[butMIMEDate expiredate=6/15/2020&expiretime=15:45]<br>
	
	Results	(On a server in the Pacific time zone at 10:30am on November 14, 2017):
	Tue, 14 Nov 2017 18:30:37 GMT
	Wed, 15 Nov 2017 20:30:37 GMT
	Mon, 15 Jun 2020 23:45:00 GMT
	
___
## <a name="butCookieExpire">butCookieExpire</a>
Returns date/time formatted for SetCookie tag

### Input
- *GMTOffset* - Hours offset from GMT to local time (optional, assumes 0)
- *years* - Years from now to expire cookie (optional)
- *months* - Months from now to expire cookie (optional)
- *days* - Days from now to expire cookie (optional)
- *hours* - Hours from now to expire cookie (optional)
- *minutes* - Minutes from now to expire cookie (optional)
- *seconds* - Seconds from now to expire cookie (optional)
- *expiredate* - Specific date to expire cookie on, formatted or days-since (optional)
- *expiretime* - Specific time of day to expire cookie, formatted or minutes-since (optional)
	
### Output
- MIME-formatted date and time string
- Format example: Wednesday, 09 Nov 1999 23:12:40 GMT

### Discussion
This function is identical to `butMIMEDate` except that it assumes that the full day name should be used ("Friday", not "Fri"). It is also a more readable function name when used in the context of a `[setcookie]` tag.

### Examples
	[setcookie name=dnatest&value=hello&expires=[butCookieExpire minutes=20]]

	Results:
	- A cookie will be set named "dnatest" with value "hello" that expires in approximately 20 minutes
	
___
## <a name="butCookieDomain">butCookieDomain</a>
Returns the domain name for this site for a SetCookie tag (eg. ".mysite.com")
This function drops a leading "www" or other host name to allow cookie to be valid throughout the full web site.

### Input
- *none*
	
### Output
- The base domain name of the current website

### Discussion
This function uses `[butHost]` to identify the fully qualified domain name, then, if the domain name includes three or more dot-separated components, the first one will be stripped leaving a leading dot. So, "www.mysite.co.uk" becomes ".mysite.co.uk", and the cookie will be accessible at any host within "mysite.co.uk", such as "secure.mysite.co.uk" or "monkeys.mysite.co.uk".

### Examples
	[setcookie name=dnatest&value=hello&expires=[butCookieExpire minutes=20]]
	[setcookie name=dnatest2&value=hello&domain=[butCookieDomain]&expires=[butCookieExpire minutes=20]]

	Results (Executed from FQDN "www.brainscansoftware.com"):
	- Cookie "dnatest" is linked to domain "www.brainscansoftware.com"
	- Cookie "dnatest2" is linked to domain ".brainscansoftware.com" and accessible to other hosts within that domain
	
	
___
## <a name="butSiteRoot">butSiteRoot</a>
Returns relative path to site root (eg. "../../")

### Input
- *DevPath* - development folder path to use as site root (optional)

### Output
- Relative path to the site root

### Discussion
Returns relative path to site root (eg. "../../") based upon folder depth of current page as determined by examining thisurl. This allows you to utilize relative links that are independent of the location of the page within your site structure. Optional "DevPath" parameter allows you to work on pages in a temporary development location with links relative to the specified path instead of the site root, then moving the file to its published location will automatically adjust relative links to reference the published page locations.

### Examples
	[butSiteRoot]<br>
	[butSiteRoot devpath=/dev/brian/]<br>

	Results (Executed from path `/dev/brian/events/myevent.html`):
	../../../
	../
	
___
## <a name="butThisPage">butThisPage</a>
Returns the name of the current page (stripped from thisurl)

### Input
- *none*
	
### Output
- File name of the current page

### Examples
	[butThisPage]

	Results (Executed from path `/dev/brian/events/myevent.html`):
	myevent.html
	
___
## <a name="butSortList">butSortList</a>
Returns sorted list of passed-in values

### Input
- **ValueList** or **direct param** - The List of values to sort (required)
- *Type* - NUM, TEXT, DATE or TIME (optional, assumes TEXT)
- *Reverse* - T to do descending sort, F to do ascending sort (optional, assumes F)
- *Delimiters* - Delimiters for `[listwords]` on the passed-in ValueList (optional, assumes WebDNA default delimters)

### Output
- The sorted list of values from the given list

### Discussion
The returned list will be delimited by commas or, if Delimiters are passed in, then the first specified delimiter.

This process is executed by loading the given values into a local `[table]`, then searching the table with the appropriate sorting method and rebuilding the list to be returned.

### Example
	[text]tList=Mike,Betty,Tim,Harry,Michelle,Abdul,LeeAnna,Zooey,Alexandra[/text]
	[butSortList ValueList=[url][tList][/url]&Reverse=T]<br>
	[text]tList=1/1/2017,11/10/1965,12/7/1942,2/2/2020,9/5/1969, June 10 1996[/text]
	[butSortList ValueList=[url][tList][/url]&Type=DATE&delimiters=,]<br>
	
	Results:
	Zooey,Tim,Mike,Michelle,LeeAnna,Harry,Betty,Alexandra,Abdul
	12/7/1942,11/10/1965,9/5/1969,1/1/2017,2/2/2020

___
## <a name="butUpdateList">butUpdateList</a>
Add or remove items from a delimited list of values

### Input
- **List** - Delimited list of values to start with (required)
- *Delimiter* - Single character to delimit the list with (optional, assumes comma)
- *Add* - Delimited list of values to add to the list, if not already there (optional)
- *Delete* - Delimited list of values to remove from the list, if there (optional)

### Output
- New list of values
	
### Discussion
When using a text variable to hold a list of values, this function is a convenient way to add or remove values in the list.

### Examples
	[text]tList=1,2,3[/text]
	[text]tList=[butUpdateList list=[url][tList][/url]&add=4,5,6&delete=2][/text]
	[tList]<br>
	[text]tSpaceList=Bob Carol Ted[/text]
	[text]tSpaceList=[butUpdateList list=[url][tSpaceList][/url]&delimiter= &add=Ross Rachel&delete=Carol Ted][/text]
	[text]tSpaceList[/text]<br>

	Results:
	1,3,4,5,6
	Bob Ross Rachel
	
___
## <a name="butWordList">butWordList</a>
Update an unordered list of unique words, adding "add" and removing "exclude" words
*Essentially a synonym for butUpdateList*

### Input
- **Words** - The word list as it previously existed
- *Add* - List of words to add to the word list
- *Exclude* - List of words to remove from the word list
- *Delimiter* - The character to use as word delimiter (defaults to comma)

### Output
- New list of words

### Discussion
I guess I wrote this twice, and used it in various places, so the synonym has been retained for compatibility.

### Examples
	[text]tList=1,2,3[/text]
	[text]tList=[butWordList words=[url][tList][/url]&add=4,5,6&exclude=2][/text]
	[tList]<br>
	[text]tSpaceList=Bob Carol Ted[/text]
	[text]tSpaceList=[butWordList words=[url][tSpaceList][/url]&delimiter= &add=Ross Rachel&exclude=Carol Ted][/text]
	[text]tSpaceList[/text]<br>

	Results:
	1,3,4,5,6
	Bob Ross Rachel
	
___
## <a name="butListContainsItem">butListContainsItem</a>
Look for one or more items in a delimited list of values

### Input
- **List** - Delimited list of values to start with (required)
- **Items** or **Item** - Delimited list of values to check for (required)
- *Delimiter* - Character to delimit the list with (optional, assumes comma)
- *All* - T if all items must be in list, F (default) if at least one item must be in list

### Output
- `[butTrue]` if item was or all items were found, else `[butFalse]`
- Global variable `[butValue]` - index in list for found item, 0 if not found

### Discussion
The items may be found at any position or in any sequence in the list. If multiple items are found, `[butValue]` is set to the index of the first found item. 

### Examples
	1: [if [butListContainsItem list=1,2,3&items=5,3]][then]Found at [butValue][/then][else]Not Found[/else][/if]<br>
	2: [if [butListContainsItem list=1,2,3&items=5,3&all=T]][then]Found at [butValue][/then][else]Not Found[/else][/if]<br>
	3: [if [butListContainsItem list=1,2,3,4,5&items=5,3&all=T]][then]Found at [butValue][/then][else]Not Found[/else][/if]<br>
	4: [if [butListContainsItem list=1 2 3 4 5&item=4&delimiters= ]][then]Found at [butValue][/then][else]Not Found[/else][/if]<br>
	5: [if [butListContainsItem list=1 2 3 4 5&item=9&delimiters= ]][then]Found at [butValue][/then][else]Not Found[/else][/if]<br>

	Results:
	1: Found at 3
	2: Not Found
	3: Found at 3
	4: Found at 4
	5: Not Found

___
## <a name="butListPosition">butListPosition</a>
Return position of a value in a delimited list of values

### Input
- **List** - Delimited list of values to start with (required)
- **Items** or **Item** - Delimited list of values to check for (required)
- *Delimiter* - Character to delimit the list with (optional, assumes comma)
- *All* - T if all items must be in list, F (default) if at least one item must be in list

### Output
- Index of item in list if found, else 0

### Examples
	[butListPosition list=Bob,Ted,Jill,Jane,Margaret&item=jill]<br>
	[butListPosition list=Bob,Ted,Jill,Jane,Margaret&item=harry]<br>
	[butListPosition list=Bob Ted Jill Jane Margaret&item=Jill&delimiter= &exact=T]<br>
	[butListPosition list=Bob Ted Jill Jane Margaret&item=jill&delimiter= &exact=T]<br>

	Results:
	3
	0
	3
	0
	
___
## <a name="butGetListItem">butGetListItem</a>
Get the value at specified index in a list of values

### Input
- **List** - The item list to look in
- **Index** - Index of the item to get
- *Delimiters* - Item delimiter characters (optional, assumes WebDNA default delimters))

### Output
- Value of the indexed item, or blank if out of range

### Discussion
This is a synonym for butGetWord (see below), for better code readability when working with lists of values rather than strings of words.

### Examples
	1:[butGetListItem list=Bob,Ted,Jill,Jane,Margaret&index=2]<br>
	2:[butGetListItem list=Bob Ted Jill Jane Margaret&index=1&delimiters= ]<br>
	3:[butGetListItem list=Bob,Ted,Jill,Jane,Margaret&index=10]<br>

	Results:
	1:Ted
	2:Bob
	3:

___
## <a name="butGetWord">butGetWord</a>
Get the word at specified index from a string

### Input
- **Words** - The words to look in
- **Index** - Index of the word to get
- *Delimiters* - Word delimiter characters (optional, assumes WebDNA default delimters))

### Output
- Value of the indexed word, or blank if out of range

### Examples
	1:[butGetWord words=Bob,Ted,Jill,Jane,Margaret&index=2]<br>
	2:[butGetWord words=Bob Ted Jill Jane Margaret&index=1&delimiters= ]<br>
	3:[butGetWord words=Bob,Ted,Jill,Jane,Margaret&index=10]<br>

	Results:
	1:Ted
	2:Bob
	3:
	
___
## <a name="butAuthorizeNet">butAuthorizeNet</a>
Posts a transaction to Authorize.Net via its AIM protocol

### Input
- *certification* - T to utilize certification.authorize.net instead of secure.authorize.net (optional, assumes F)
- *(any AIM param)* - Parameter to be added to the request - leading "x_" is optional in paramter names (e.g. "x_login" and "login" are treated the same)

### Output
- `[butTrue]` if approved, or `[butFalse]` if declined or error
- Global variable `[butResponse]` is set to the full response string returned by Authorize.Net

### Discussion
This has not been used or updated in a while, but it did make interaction with Authorize.net much simpler to implement.

### Examples
	[if [butAuthorizeNet ...]][then]
		... transaction approved ...
		... get authorization code from butResponse ...
	[/then][else]
		... transaction declined or error ...
		... get details from butResponse ...
	[/else][/if]

___
## <a name="butTCPFetch">butTCPFetch</a>
Gets content from a web page via TCPConnect

### Input
- **Address** or **direct parameter** - URL to access, begining with http:// or https://
- *StartAfter* - For a MIDDLE on the returned content (optional)
- *EndBefore* - For a MIDDLE on the returned content (optional)
- *SkipHeader* - T to skip the returned headers (optional, assumes F)
- *Post* - Data to POST to page (e.g. name=value&name2=value2)

### Output
- Returns content of the page without the headers
- Global variable `[butHeaders]` set to page headers, unless SkipHeader = T

### Discussion
This function makes it very simple to load content from another URL, handling proper formatting of request parameters, incorporating the necessary `[tcpconnect]` and `[tcpsend]` contexts, and optionally extracting just the desired content via a `[middle]` context.

### Examples
	[butTCPFetch address=[url]http://www.google.com/[/url]&startafter=</head>&endbefore=</html>]

	Results:
	- Contents of the Google home page
	
___
## <a name="butShowNonBlank">butShowNonBlank</a>
Show value with optional prefix and suffix if value is not blank

### Input
- **Value** - The value to check and/or show
- *Prefix* - Text to insert before non-blank value (optional)
- *Suffix* - Text to insert after non-blank value (optional)

### Output
- Nothing if value is blank
- (prefix)(value)(suffix) if value is not blank

### Discussion
Convenient for displaying values only if a field or variable is not blank. Prefix and Suffix are handy for adding HTML before or after the value.

### Examples
	[text]tVal=[/text]
	1: [butShowNonBlank value=[tVal]&prefix=<b>&suffix=</b>]<br>
	[text]tVal=Baloon[/text]
	2: [butShowNonBlank value=[tVal]&prefix=<b>&suffix=</b>]<br>

	Results:
	1: 
	2: __Baloon__

___
## <a name="butAddressFormat">butAddressFormat</a>
Format parameters as an address (U.S.)

### Input
- *Address* - Street or PO box address, multiple lines supported
- *City* - City name
- *State* - State name or abbreviation
- *Zip* - Zip code
- *Country* - Country name
- *Break* - Line break string, default "<br />"

### Output
- Best-formatted address given the data available

### Discussion
This function will format the US address data as best it can given the data available. Line breaks, commas, spaces are dependent upon whether the appropriate values are blank or not. See examples for clarification.

### Examples
	[butAddressFormat address=1313 Mocking Bird Lane%0DApartment 13&city=Los Angeles]<br><br>
	[butAddressFormat address=1313 Mocking Bird Lane&city=Los Angeles&state=CA&zip=98765]<br><br>
	[butAddressFormat address=1313 Mocking Bird Lane&city=Los Angeles&state=CA&zip=98765&country=USA]<br><br>

	Results:
	1313 Mocking Bird Lane
	Apartment 13
	Los Angeles

	1313 Mocking Bird Lane
	Los Angeles, CA 98765

	1313 Mocking Bird Lane
	Los Angeles, CA 98765
	USA

___
## <a name="butPhoneFormat">butPhoneFormat</a>
Format value as a phone number

### Input
- **Number** or **direct parameter** - Phone number value to be formatted
- *Chars* - Allowable characters for GREP (optional, default "0-9A-Z")
- *PhoneFormat* - Formatting specifier, (optional, default "(3)3-4?xN")

### Output
- Formatted phone number

### Discussion
The Chars value is used to strip unwanted characters from the given Number string.

If the `Number` is exactly 7 characters long and no `PhoneFormat` is specified, then the `PhoneFormat` defaults to "3-4", for a standard US phone number with no area code (e.g. "487-6066").

Formatting is based on the following characters in the format string:
- Digits specify number of characters
- N is variable length (all remaining chars)
- ? is point to stop at if no chars remaining
- other chars are literals

Given an input of "123.456.7890, extension 1234", using the default Chars and PhoneFormat values, this function would perform the following steps:
- Grep out the unwanted characters, leaving 12345678901234
- Insert a literal "(" into the output string, giving "("
- Insert the first three characters of the number, giving "(123"
- Insert a literal ")", giving "(123)"
- Insert the next three characters, giving "(123)456"
- Insert a literal "-", giving "(123)456-"
- Insert the next 4 characters, giving "(123)456-7890"
- Interpret the "?" option - If there were no input characters remaining, the string would stop there, but there are remaining characters, so...
- Insert the literal "x", giving "(123)456-7890x"
- Insert the remaining N characters, giving "(123)456-7890x1234"

### Examples
	[butPhoneFormat 123.456.7890, extension 1234]<br>
	[butPhoneFormat number=123.456.CALL]<br>
	[butPhoneFormat number=0123.456.7890 Ext 77, extension 1234&Chars=0-9&PhoneFormat=1*3-3-4xN]<br>
	[butPhoneFormat 12.1234]<br>
	[butPhoneFormat number=555 1212]<br>

	Results:
	(123)456-7890x1234
	(123)456-CALL
	0*123-456-7890x77
	555-1212

	
___
## <a name="butAge">butAge</a>
Determine an age based on the date of birth and the current or specified date

### Input
- **DOB** or **direct parameter** - Date of birth, as math "days since 12/31/-0001" or math friendly text format
- *AsOf* - Date to calculate age as of (optional, assumes today)

### Output
- Return value - age in years
- Global variable `[butMonths]` set to number of months beyond returned years
- Global variable `[butDays]` set to number of days beyond returned months
- Global variable `[butFuture]` set to `[butTrue]` if DOB is after AsOf, else `[butFalse]`

### Examples
	On January 1, 2020, you will be [butAge DOB=6/10/1985&AsOf=1/1/2020] years, [butMonths] months and [butDays] days old.<br>

	The Magna Carta was signed [butAge DOB=6/15/1215] years, [butMonths] months and [butDays] days ago.<br>

	[text]tYears=[butAge 12/25/[date %Y]][/text]
	[if [butFuture]][then]
		Christmas is [butMonths] months and [butDays] days from today.<br>
	[/then][else]
		Christmas was [butDays] days ago.<br>
	[/else][/if]

	[text]tYears=[butAge 12/25/[date %Y]&asof=12/28/2017][/text]
	[if [butFuture]][then]
		Christmas is [butMonths] months and [butDays] days from today.<br>
	[/then][else]
		Christmas was [butDays] days ago.<br>
	[/else][/if]
		
	Results (Executed on November 15, 2017):
	On January 1, 2020, you will be 34 years, 6 months and 22 days old.
	The Magna Carta was signed 802 years, 5 months and 0 days ago.
	Christmas is 1 months and 10 days from today.
	Christmas was 3 days ago.
	
___
## <a name="butZip">butZip</a>
Use shell "zip" command to create an archive of one or more files

### Input
- **Root** - starting folder path for archive contents
- **ZipFile** - path (full or relative to document) to archive file to create or update
- *File* or *Files*	- space-delimited list of files and folders to zip, relative to "root" (optional, defaults to "*")
- *Recursive* - T (default) to recurse into folders, F to not
- *Move* - T to move files into zip (deleting originals), F (default) to copy files into zip (leaving originals in place)
- *Clean* - T to delete zip file first if it exists, F (default) to append new files to existing zip file
- *Skip* - space-delimited list of files (not folders) to skip, relative to `Root`

### Output
- `[butTrue]` if successful, `[butFalse]` if not
- Global variable `[butError]` set to error message if there was a problem

### Examples
	[if [butZip Root=/brainscan&ZipFile=/brainscan/library.zip&files=library&clean=T]][then]
		Good - archive "/brainscan/library.zip" has been created
	[/then][else]
		Bad - [butError]
	[/else][/if]

	Results:
	- If folder "/brainscan/library" exists, then:
		Good - archive "/brainscan/library.zip" has been created
	- If not, then:
		Bad - butZip: Root "/brainscan" not found.
	- or:
		Bad - File/Folder "library" does not exist.
	
___
## <a name="butLoadRecord">butLoadRecord</a>
Search for a record and store its fields in global text variables

### Input
- **DB** - Path to the database to search
- **Param** - Parameters for the search (e.g. "[url]eqField1datarq=Herman[/url]")
- *Fields* - List of fields to save (optional, assumes all fields in db)
- *Prefix* - Prefix for text variables saved (optional, assumes none)
- *NotFound* - T to create empty variables when no record found, F to report error

### Output
	Returns butTrue if successful
	Global variables set
	butError	-	error message on failure or on multiple found records

### Discussion
This is a convenient way to load a database record that needs to be accessible further down the page, without having to stay inside a `[search ...][founditems]` context. This is especially useful if there might be multiple ways of identifying the record.

*Param* parameter notes: remember to `[url]` the entire contents of the `[param]` parameter. For example, if searching by a text field named `myKeyField` based on a form value entered by the user and received in form variable `enteredKeyData`, your call may look like this:
	[butLoadRecord db=/db/myData.db&param=[url]myKeyField=[url][enteredKeyData][/url][/url]]

For example, loading a record from a `user.db` where you might look it up by a `userID` number, or you might look it up using a `userEmail` address, depending on the parameters passed in to the page. See the example below for how this might be handled.

*Prefix* parameter notes: If your database has fields `myID`, `myKeyField`, and `myDescription`, and you do not provide a `Prefix`, then text variables with the exact same names will be created, which can be confusing if you will be performing another search on the same database later. In cases like this, it is helpful to provide a prefix such as `Prefix=found`, which would then generate text variables named `foundmyID`, `foundmyKeyField`, and `foundmyDescription`.

*NotFound* parameter notes: setting `NotFound=T` can be convenient in situations such as displaying a record in an "edit" form, which will double as an "add" form with values defaulted to blank if no existing record was found.

### Example 1
	[if [butLoadRecord db=/db/users.db&equserIDdatarq=[formUserID]]][then]
		Found user by User ID.<br>
	[/then][else]
		[if [butLoadRecord db=/db/users.db&equserEmaildatarq=[formEmailAddress]&notfound=T]][then]
			Found user by Email Address.<br>
		[/then][else]
			User not found.<br>
			[text]userName=New User[/text]
		[/else][/if]
	[/else][/if]
	Hello, [userName]!
	
	Results:
	- If found user "Barney Rubble" by ID:
	Found user by User ID.
	Hello, Barney Rubble!

	- If found user "Pebbles Flintstone" by Email Address:
	Found user by Email Address.
	Hello, Pebbles Flintstone!

	- If no user was found:
	User not found.
	Hello, New User!

### Example 2
	
	[writefile /db/test.db]a	b	c
	1	2	3
	4	5	6
	[/writefile]

	[if [butLoadRecord db=/db/test.db&param=[url]eqadatarq=4[/url]&prefix=x]][then]
		[Xa] - [Xb] - [Xc]<br>
	[/then][else]
		[butError]<br>
	[/else][/if]
	[if [butLoadRecord db=/db/test.db&param=[url]eqadatarq=NOPE[/url]&prefix=x]][then]
		[Xa] - [Xb] - [Xc]<br>
	[/then][else]
		[butError]<br>
	[/else][/if]

	Results:
	4 - 5 - 6
	butLoadRecord: No records found for (search db=/brainscan/test.db&eqadatarq=NOPE&max=1).

___
## <a name="butFedExLink">butFedExLink</a>
Return URL for shipment tracking via FedEx

### Input
- **Tracking** or **direct parameter** - One or multiple tracking numbers
- *Country* - Country code (optional, assumes "us")
- *Language* - Language (optional, assumes "english")

### Output
- URL for FedEx Tracking link

### Discussion
This is a convenient way to provide the user with a link to FedEx's website for package tracking. To provide tracking information within your page, see `[butFedExTracking]` below.

### Examples
	[text]trackingNumbers=9999999999,8888888888[/text]
	<a href="[butFedExLink tracking=[trackingNumbers]]" target="_blank">Track Shipments</a>

	Results:
	<a href="http://www.fedex.com/Tracking?cntry_code=us&language=english&tracknumbers=9999999999,8888888888" target="_blank">Track Shipments</a>

___
## <a name="butFedExTracking">butFedExTracking</a>
Fetch FedEx Tracking status information and store into global text variables
**THIS FUNCTION IS BROKEN - DO NOT USE AS IS**

### Input
- **Tracking** or **direct parameter** - One (and only one) tracking number
- *Country* - Country code (optional, assumes "us")
- *Language* - Language (optional, assumes "english")

### Output
	true if successful, false if failure
	The following are set with text values (you need to parse dates yourself if desired)
	butFXURL
	butFXNumber
	butFXStatus
	butFXSignedBy
	butFXShipDate
	butFXEstimatedDelivery
	butFXDeliveryDate
	butFXReference
	butFXDestination
	butFXServiceType

### Discussion
This function was built using a screen-scarping method, which breaks whenever FedEx updates their page structure. This should be rewritten using published APIs, but I don't have time (or use) for that right now.

### Examples
	[if [butFedExTracking 8888888888]][then]
		[butFXStatus]<br>
	[/then][else]
		[butError]<br>
	[/else][/if]

	Results:
	- Should show status if tracking number is valid
	
___
## <a name="butUPSLink">butUPSLink</a>
Return URL for shipment tracking via UPS

### Input
- **Tracking** or **direct parameter** - One or multiple tracking numbers
- *Country* - Country code (optional, assumes "us")
- *Language* - Language (optional, assumes "english")

### Output
- URL for UPS Tracking link

### Discussion
This is a convenient way to provide the user with a link to UPS's website for package tracking.

### Examples
	[text]trackingNumbers=1Z9999999999,1Z8888888888[/text]
	<a href="[butUPSLink tracking=[trackingNumbers]]" target="_blank">Track Shipments</a>

	Results:
	<a href="http://wwwapps.ups.com/WebTracking/OnlineTool?TypeOfInquiryNumber=T&UPS_HTML_Version=3.0&IATA=us&Lang=eng&InquiryNumber1=1Z9999999999&InquiryNumber2=1Z8888888888" target="_blank">Track Shipments</a>
	
___
## <a name="butShippingLink">butShippingLink</a>
Determines shipping company and returns URL for tracking

### Input
- **Tracking** or **direct parameter** - tracking number
- *Carrier* - specify carrier name (optional)

### Output
- URL for Tracking link at specified or defaulted carrier

### Discussion
`Carrier` values supported include `FedEx`, `UPS`, `USPS`, and `DHL`.

If no `Carrier` is specified, this function will try to identify the carrier by the format of the tracking number. If the tracking number begins with "1Z", then `UPS` is assumed, otherwise `FedEx` is assumed.

### Examples
	[butShippingLink Tracking=1234567890&Carrier=DHL]<br>
	[butShippingLink Tracking=1Z1234567890]<br>
	[butShippingLink Tracking=1234567890]<br>
	
	Results:
	- Tracking URL at DHL
	- Tracking URL at UPS
	- Tracking URL at FedEx
	
___
## <a name="butShortenString">butShortenString</a>
Show part of a string with inserted ellipsis

### Input
- **String** - The incoming string of characters
- **Max** - The maximum character count of the resulting string (defaults to whole string)
- **Tail** - Number of tail characters to include (defaults to 0)
- **Insert** - String to insert where characters were removed (defaults to ellipsis (&hellip;))
- Break - Word, delimiter list or Char (Character) break (defaults to char)

### Output
- Shortened string

### Discussion
When you have a long string of text to be displayed in a short amount of space, it is sometimes convenient to show a portion of the string with an indicator that there is more text available, such as in a listing of file names when some of the names are very long, or showing a preview of a longer article with a link to view the whole thing.

### Examples
	[text]tString=This is a long string of text, and we want to shorten it.[/text]
	[butShortenString string=[url][tString][/url]&max=40&break=word]<br>
	[butShortenString string=[url][tString][/url]&max=40&break=word&tail=5]<br>
	[butShortenString string=[url][tString][/url]&max=40&break=char&tail=5&insert=___]<br>

	Results:
	This is a long string of text, and we…
	This is a long string of text, and…it.
	This is a long string of text, and ___n it.
	
___
## <a name="butCountOccurrences">butCountOccurrences</a>
Count the number of times one string occurs within another.

### Input
- **String** - The string to look in
- **Find** - The string to look for

### Output
- Integer count of the number of times `[Find]` occurs within `[String]`

### Examples
	[butCountOccurrences string=monkey see monkey do&find=turtle]<br>
	[butCountOccurrences string=monkey see monkey do&find=see]<br>
	[butCountOccurrences string=monkey see monkey do&find=monkey]<br>

	Results:
	0
	1
	2
	
___
## <a name="butFileSize">butFileSize</a>
Convert Byte count to friendly view - KB, MB, GB, TB

### Input
- **Bytes** or **direct param** - File size in bytes (this or Path is required)
- **Path** - or... Path to the file to get the size of (this or Bytes is required)
- *Precision* - Number of digits after the decimal to show (default 1)
- *KSsize* - Size of 1K (default 1000) - may want 1024 for some uses
- *Spaced* - Space between number and units? (default F)

### Output
- Friendlier version of byte size

### Discussion
When displaying sizes of large files for users, it is often preferred to give an approximate size in KB, MB, GB, etc. to make it more readable to the user.

### Examples
	[butFileSize Path=[thisurl]]<br>
	[butFileSize Bytes=12345567890&Precision=2]<br>
	[butFileSize Bytes=12345567890&Precision=2&KSize=1024&Spaced=T]<br>

	Results:
	4.8KB (depending on the actual file size of your page)
	12.35GB
	11.50 GB *note the significantly different representation of the same value

___
## <a name="butCSVValue">butCSVValue</a>
Map WebDNA DB characters (returns, tabs)
Quote value if contains comma or line ender
Quotes become quotequote

### Input
- **direct parameter** - Value to be encoded

### Output
- CSV-encoded value

### Discussion
When exporting to CSV format, returns, tabs and quotes within a field must be escaped and/or quoted.

### Examples
	[url][butCSVValue My name is "Harry"][/url]<br>
	[url][butCSVValue Frog(tab)Monkey(return)Turtle][/url]<br>

	Results:
	My%20name%20is%20%22%22Harry%22%22
	%22Frog%09Monkey%0D%0ATurtle%22

___
## <a name="butTextMap">butTextMap</a>
Map as text, html code shows on the page

### Input
- **direct parameter** - Text to be mapped

### Output
- Mapped text

### Discussion
The primary use case for this function is when displaying text from a field in a database where you do not want to interpret any HTML tags, but rather to display them visibly on the page. This is a good mapping to use when displaying content entered into a form by an untrusted web site user.

The ConvertChars mapping table used by this function includes:

- BR tags substituted for carriage returns
- TAB characters substituted for WebDNA's %1D mapping of saved TABs
- HTML Entities substituted for Ampersand, Registered Trademark, Copyright, Trademark, Left Angle Bracket, Right Angle Bracket, Degree
- Straight single- and double-quotes substituted for curly ones

### Examples
	[butTextMap &©<br>“hello”]<br>
	[url][butTextMap &©<br>“hello”][/url]

	Results:
	&©
	“hello”
	%26amp%3B%A9%26lt%3Bbr%26gt%3B%93hello%94
	
___
## <a name="butTextMapRaw">butTextMapRaw</a>
Map as text, just converting line enders and tabs

### Input
- **direct parameter** - Text to be mapped

### Output
- Mapped text

### Discussion
This is the simple text mapping case that only reverts WebDNA's automatic character mapping of TABs and Carriage Returns, returning the text as it was initially provided to WebDNA for saving to a database.

The ConvertChars mapping table used by this function includes:

- CR characters substituted for %0B mapping of saved CRs
- TAB characters substituted for WebDNA's %1D mapping of saved TABs

### Examples
	<pre>[butTextMapRaw [unurl]A%1DB%1D<b>C</b>%0B1%1D2%1D<i>3</i>%0B[/unurl]]</pre>

	Results:
	A	B	<b>C</b>
	1	2	<i>3</i>
	
___
## <a name="butHTMLMap">butHTMLMap</a>
Map as HTML, adding line breaks at returns

### Input
- **direct parameter** - Text to be mapped

### Output
- Mapped text

### Discussion
The primary use case for this function is when displaying text from a field in a database where you want to allow HTML markup, with automatic HTML line breaks where the user entered them. This mapping should only be used when the contentent being displayed was entered by a trusted web site admin.

User-entered carriage returns are mapped to `<br />` tags, so simply entering text in paragraphs will result in line breaks where the user expects them.

The ConvertChars mapping table used by this function includes:

- `<br />` tags substituted for carriage returns
- TAB characters substituted for WebDNA's %1D mapping of saved TABs
- Left and Right Angle Brackets are left as-is, so HTML will be rendered by the browser
- HTML Entities substituted for Ampersand, Registered Trademark, Copyright, Trademark, Degree
- Straight single- and double-quotes substituted for curly ones

### Examples
	[butHTMLMap &©<br>“hello”
	Newman]<br>
	<br>
	[url][butHTMLMap &©<br>“hello”
	Newman][/url]<br>

	Results:
	&©
	"hello"
	Newman
	
	%26%26copy%3B%3Cbr%3E%22hello%22%3Cbr%20/%3ENewman

___
## <a name="butHTMLNoBreakMap">butHTMLNoBreakMap</a>
Map as HTML, no added line breaks

### Input
- **direct parameter** - Text to be mapped

### Output
- Mapped text

### Discussion
The primary use case for this function is when displaying text from a field in a database where you want to allow HTML markup, without the automatic HTML line breaks created by `[butHTMLMap]`. This mapping should only be used when the contentent being displayed was entered by a trusted web site admin.

User-entered carriage returns not mapped to `<br />` tags, if more complex HTML is entered, such as tables or lists, the user may include line breaks for code readability without causing problems with the resulting HTML.

The ConvertChars mapping table used by this function includes:

- CR characters substituted for WebDNA's %0B mapping of saved CRs
- TAB characters substituted for WebDNA's %1D mapping of saved TABs
- Left and Right Angle Brackets are left as-is, so HTML will be rendered by the browser
- HTML Entities substituted for Ampersand, Registered Trademark, Copyright, Trademark, Degree
- Straight single- and double-quotes substituted for curly ones

### Examples
	[butHTMLNoBreakMap &©<br>“hello”
	Newman]<br>
	<br>
	[url][butHTMLNoBreakMap &©<br>“hello”
	Newman][/url]<br>

	Results:
	&©
	"hello"Newman
	
	%26%26copy%3B%3Cbr%3E%22hello%22%0DNewman

___
## <a name="butUTF">butUTF8Map</a>

### Input
- **direct parameter** - Text to be mapped

### Output
- Mapped text

### Discussion
This function will map ISO-8859-1 Extended ASCII text to UTF-8 Unicode characters.

### Examples
	[text]tASCII=[unurl]%99%9F%A0%A5%E7[/unurl][/text]
	ASCII: [url][tASCII][/url]<br>
	UTF-8: [url][butUTF8Map [unurl]%99%9F%A0%A5%E7[/unurl]][/url]<br>

	Results:
	ASCII: %99%9F%A0%A5%E7
	UTF-8: %99%9F%C2%A0%C2%A5%C3%A7
___
## <a name="butEntityMap">butEntityMap</a>
Map ASCII characters to their HTML Entity equivalents.

### Input
- **direct parameter** - Text to be mapped

### Output
- Entity-mapped version of text

### Examples
	[butEntityMap [unurl]%93%99%94 "<>"[/unurl]]<br>
	[url][butEntityMap [unurl]%93%99%94 "<>"[/unurl]][/url]<br>

	Results:
	“™” "<>"
	%26ldquo%3B%26trade%3B%26rdquo%3B%20%26quot%3B%26lt%3B%26gt%3B%26quot%3B
	
___
## <a name="butEditMap">butEditMap</a>
Map text in preparation for display in a `TEXTAREA` form field.

### Input
- **direct parameter** - Text to be mapped

### Output
- Mapped text

### Discussion
This mapping function takes the hassle out of displaying content from a database field in a `TEXTAREA` field in a web form. Characters are mapped to the appropriate entities and line enders to be properly displayed.

### Examples
	<textarea rows="5" cols="80">[butEditMap [unurl]“Hello,” said she.%0B%0BHe just shrugged.[/unurl]]</textarea><br>
	[url][butEditMap [unurl]“Hello,” said she.%0B%0BHe just shrugged.[/unurl]][/url]<br>
	
	Results:
	- TEXTAREA with properly displayed content
		%26ldquo%3BHello%2C%26rdquo%3B%20said%20she.%26%23013%3B%26%23013%3BHe%20just%20shrugged.
	
___
## <a name="butSmartMap">butSmartMap</a>
Map text for display from database, intelligently choosing whether to map HTML and line breaks

### Input
- **direct parameter** - Text to be mapped

### Output
- Mapped text

### Discussion
If text contains <br, <p or <table, map carriage returns to nothing

If not, map carriage returns to <br />

The point here is that if there are no HTML line, paragraph or table tags in the text, we should treat all carriage returns as line breaks. If there are, then trust the author of the content to have put in all the HTML markup they want.

### Examples
	[butSmartMap Line <b>one</b>[unurl]%0B%0B[/unurl]Line <b>two</b>]
	<br><br>
	[butSmartMap Line <b>three</b><br />[unurl]%0B%0B[/unurl]Line <b>four</b>]

	Results:
	Line <b>one</b>

	Line <b>two</b>

	Line <b>three</b>
	Line <b>four</b>
		
___
## <a name="VersionHistory">Version History</a>
	Version		Date		Who				Changes
			27Jan2004	Brian Fries		Initial development
			06Feb2004	Brian Fries		Added butInc and butElapsedTime functions
			24Mar2004	Brian Fries		Added butVersion and butFunctions functions
			19May2004	Brian Fries		Added butDaysToDate and butSecondsToTime functions
			21May2004	Brian Fries		Added butIsDefined, butIsTextVar, butIsMathVar, butIsFormVar
			25May2004	Brian Fries		Added butIsNumeric, butCookieExpire, butCookieDomain, butSiteRoot, butThisPage
			26May2004	Brian Fries		Added butListToArray
			28May2004	Brian Fries		Added butAuthorizeNet
			31May2004	Brian Fries		Added WebDNA version test in butListToArray to avoid crashing bug (blank array value)
			18Jun2004	Brian Fries		Added butTrim
			27Jun2004	Brian Fries		Added butHost
			01Jul2004	Brian Fries		Added butTCPFetch, butShowHTML, butMIMEDate
			09Jul2004	Brian Fries		Added butIsEmpty
			01Oct2004	Brian Fries		Added butTextSet, butMathSet, butArraySet, loaded toggle variable
			08Oct2004	Brian Fries		Added butToday, butNow
			14Oct2004	Brian Fries		Support direct parameter with default format to butDaysToDate and butSecondsToTime
			19Oct2004	Brian Fries		Added butPhoneFormat, define butTrue and butFalse
			25Oct2004	Brian Fries		Support butPhoneFormat on WebDNA 5 (no listchars)
			01Nov2004	Brian Fries		Added %0B and %1D to butTrim characters
			08Nov2004	Brian Fries		Added butAge function
			19Nov2004	Brian Fries		Added butIsInteger function
			20Dec2004	Brian Fries		Fixed syntax error in butPhoneFormat
			18Jan2005	Brian Fries		Added butIsFile and butIsFolder functions; use :local: in referencing parameters
			24May2005	Brian Fries		Eliminate confusing characters from butPassword generator (l1IO0); Add butZip
			25May2005	Brian Fries		Fixed butZip to work on systems without Absolute Path prefix (*) enabled 
			29Jun2005	Brian Fries		Set butValue global from butIsDefined, butIsTextVar, butIsMathVar and butIsFormVar
			08Sep2005	Brian Fries		Added "Friendly" parameter to butDaysToDate (strip leading zeroes from %d and %m values)
			25Oct2005	Brian Fries		Added "Friendly" parameter to butToday (use butDaysToDate)
			07Nov2005	Brian Fries		Fixed Friendly dates when %d or %m starts the format string; Cleaner handling of friendly param to butToday with no dateformat param;
								Added Friendly and Lower params to butNow and butSecondsToTime (strip zeroes from %I values; lowercase am/pm)
			02Mar2006	Brian Fries		Added butLoadRecord, butIsLower, butIsUpper, butExactMatch
			04May2006	Brian Fries		Added butFedExLink
			06Jun2006	Brian Fries		Added butCapitalize
			21Jun2006	Brian Fries		Added butDec
			03Mar2007	Brian Fries		Added butTextMap, butHTMLMap, butHTMLNoBreakMap and butSmartMap
			16Mar2007	Brian Fries		Added butRandom
			14Dec2007	Brian Fries		Added butFedExTracking
			17Dec2007	Brian Fries		Bug fix in butFedExTracking
			12Jan2008	Brian Fries		Added _butTimePatch to fix seconds_to_time but in Linux version
			04Apr2008	Brian Fries		Added butNotDefined
			23May2008	Brian Fries		New URL for to butFedExTracking; added sanity checks
			04Feb2009	Brian Fries		Updated butFedExTracking for new FedEx page layout
			09Apr2010	Brian Fries		Fixed "max" bug in butRandom
								Added butShortenString
	01.00.00b19	09Dec2010	Brian Fries		Added butEndsWith
	01.00.00b20	20Sep2011	Brian Fries		Added butSpellNumber
	01.00.00b21	21Sep2011	Brian Fries		Add www. prefix to fedex.com links
	01.00.00b22	06Mar2012	Brian Fries		Add butFunctionParam, butFunctionParamList
	01.00.00b23	12Mar2012	Brian Fries		Enhanced butTrim to strip trailing whitespace from each line
	01.00.00b24	20Mar2012	Brian Fries		Add butShowNonBlank, butAddressFormat, Changed butVersion to a text var
	01.00.00b25	28Mar2012	Brian Fries		Support <br /> in butSmartMap
	01.00.00b26	29Mar2012	Brian Fries		Add butTextMapRaw
	01.00.00b27	23Apr2012	Brian Fries		Add butDefaultValue
	01.00.00b28	03May2012	Brian Fries		Added butGetWord
	01.00.00b29	16May2012	Brian Fries		Added butWeekdayOffset
	01.00.00b30	05Jun2012	Brian Fries		Added &eacute; to text conversions
	01.00.00b31	12Jun2012	Brian Fries		Added "break" parameter to butAddressFormat; Use <br /> throughout
	01.00.00b32	25Jun2012	Brian Fries		Added butUpdateList
				26Jul2012	Rob Freiburger	Added butUPSLink
				26Jul2012	Rob Freiburger	Added butShippingLink
	01.00.00b33	14Aug2012	Brian Fries		Added butFileSize
	01.00.00b34	06Nov2012	Brian Fries		Fixed butTCPFetch to include trailing slash if provided
	01.00.00b35	29Nov2012	Brian Fries		Fixed butAddressFormat to add line break between street and city
	01.00.00b36	18Dec2012	Brian Fries		Added and used butGetWebDNAPref, supporting both WebCatalog Prefs and webdna.ini
								Updated butFunctionParam for WebDNA 7 compatibility (can't use defined keywords like "default" as parameters)
								... Probably gonna need more work along these lines
								Converted to TEXT encapsulation instead of comments
	01.00.00b37	16Jan2013	Brian Fries		Added POST support to butTCPFetch
	01.00.00b38	19Jan2013	Brian Fries		Added butWordList
	01.00.00b39	26Feb2013	Brian Fries		Added butExponent, butRound
	01.00.00b40	10Apr2013	Brian Fries		Added butISO1Map, butUTF8Map, butEntityMap, butEditMap, butAsciiCodeMap, butCountOccurrences
	01.00.00b41	19Jan2013	Brian Fries		Added butListContainsItem
	01.00.00b42	26Jun2013	Brian Fries		Added TRIM parameter to butFunctionParam
	01.00.00b43	13Jan2014	Brian Fries		Accept item as synonym for items in butListContainsItem
								Added butListPosition
	01.00.00b44	04Feb2014	Brian Fries		50% faster version of butFunctionParam
	01.00.00b45	19Feb2014	Brian Fries		Added butSplitMixedCaseWord
	01.00.00b46	21Feb2014	Brian Fries		Fixed butSplitMixedCaseWord to keep runs of caps together
	01.00.00b47	05Mar2014	Brian Fries		Fixed trim param broken in rewrite of butFunctionParam
	01.00.00b48	16Sep2014	Brian Fries		FedExLink uses comma instead of %0D%0A as delimiter now
	01.00.00b49	14Oct2014	Brian Fries		Added butCSVValue; make butPhoneFormat default to 3-4 format if exactly 7 characters passed in
	01.00.00b50	15Jan2015	Brian Fries		Added butIDTagComponents
	01.00.00b51	17Jan2015	Brian Fries		Added special characters butVLF, butCR, butLF, butTab, butVTB
								Fixed butTrim to not unurl parameter unless it contains a % - because [unurl]+[/unurl] maps to a space
	01.00.00b52	07Jan2016	Brian Fries		Added curly quotes to butEntityTable; Map %u201D to right double curly quote
	01.00.00b53	07Jun2016	Brian Fries		Fixed reference to "delimiter" parameter in butListContainsItem
								Cleaned up some code to pass syntax check
	01.00.00b54	11Aug2016	Brian Fries		Added USPS and DHL support to butShippingLink; also added carrier parameter
	01.00.00b55	11Aug2016	Brian Fries		Accept "delimiter" or "delimiters" parameters interchangeably throughout
	01.00.00b56	22Sep2016	Brian Fries		Rewrote butFunctionParam to support WebDNA 8+, which didn't like the "default" parameter
	01.00.00b57	25Jul2017	Brian Fries		Fixed butFunctionParm to work in WebDNA 8.1 where :local:default makes things fail
	01.00.00b58	18Oct2017	Brian Fries		URL properly in butMax and butMin when doing alpha comparison
								Added scope parameter to butIsTextVar and butIsMathVar
	01.00.00	21Nov2017	Brian Fries		Adapted for public use and released to Github
								Added butIsAlpha, butIsAlphanumeric
								Numerous bug fixes, thanks to unit testing
											