# httpBL-CodeIgniter

Make use of the Project Honey Pot http:BL in CodeIgniter.

## Requirements

1. PHP 5.1+
2. CodeIgniter 2.0.x - 2.0-dev
3. http:BL Access Key

## Features

* Simple interface into the Honey Pot Project's http:BL API
* Choice of responses (Standard, Pretty, Developer)
* Search Engine detection
* Debugging information

## Examples

	$this->load->library('httpbl'); 

### Standard response

This function returns the standard http:BL API response

	// Retrieve standard response
	$this->httpbl->standard('216.239.57.99');

Output:

	127.0.0.3

### Pretty response

This function returns a detailed version of the http:BL API response

	// Retrieve pretty response
	$this->httpbl->pretty('216.239.57.99');

Output:

	<font color="red"><b>Dangerous IP</b></font><br /><br /><b>IP Address: </b>60.182.190.2<br /><b>Type:</b> Suspicious & Comment Spammer<br /><b>Threat Level: </b>21 out of 255<br /><b>Last Seen: </b>1 day ago<br />

### Developer response

This function returns the standard response but in a PHP array, JSON or XML format.

	// Retrieve developer response
	$this->httpbl->dev('216.239.57.99');

Output:

	Array ( [int] => 127 [days] => 1 [threat] => 21 [type] => 5 )

The default developer response is set to PHP array. For JSON or XML pass a second arguement.

	// Retrieve developer response in JSON
	$this->httpbl->dev('216.239.57.99','json');

Output:

	{
		"int": 127,
		"days": 1,
		"threat": 21,
		"type": 5
	}

	## Download

http://chriz.co.uk/ci/sparks/httpbl-codeigniter/
	