<div align="center">

## Session ID


</div>

### Description

Generate a random string of caracters to use for identifying your users on your web site. Can also be used to generate passwords.
 
### More Info
 
nSize , number of caracters for the string default =24

Uses PHP.

A string with the random caracters in it.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Benoit Gauthier](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/benoit-gauthier.md)
**Level**          |Beginner
**User Rating**    |4.8 (24 globes from 5 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Strings](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/strings__8-26.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/benoit-gauthier-session-id__8-225/archive/master.zip)

### API Declarations

No Copyrights, use as is.


### Source Code

```
<?
	//----------------------------------------------------
	// Function GetSID()
	//
	// Parameters : $nSize number of caracters, default 24
	// Return value : 24 caracters string
	//
	// Description : This function returns a random string
	// of 24 caracters that can be used to identify users
	// on your web site in a more secure way. You can also
	// use this function to generate passwords.
	//----------------------------------------------------
	function GetSID ($nSize=24) {
		// Randomize
		mt_srand ((double) microtime() * 1000000);
		for ($i=1; $i<=$nSize; $i++) {
			// if you wish to add numbers in your string,
			// uncomment the two lines that are commented
			// in the if statement
			$nRandom = mt_rand(1,30);
			if ($nRandom <= 10) {
				// Uppercase letters
				$sessionID .= chr(mt_rand(65,90));
		//	} elseif ($nRandom <= 20) {
		//		$sessionID .= mt_rand(0,9);
			} else {
				// Lowercase letters
				$sessionID .= chr(mt_rand(97,122));
			}
		}
		return $sessionID;
	}
	// Test the function
	echo GetSID(16);
?>
```

