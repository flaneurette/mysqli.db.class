# class.DB
Minimal PHP database class.

A minimal and lean PHP mysqli database class. 256 lines of code.

Examples of use:

OPEN DB
  ------
	$db = new sql();

SELECT:
  ------
	$table    = 'test';
	$column   = 'id';
	$value    =  1;
	$operator = '*';
	
	$test = $db->select($table,$operator,$column,$value);
	// becomes: select * from test where id = 1
    	echo "<pre>". print_r($test) . "</pre>";

COUNT
  ------ 
	$table  = 'test';
	$column = 'foo'
	$value  = 'abc';
	$db->countrows($table,$column,$value);
	
INSERT:
  ------ 
	$table   = 'test';
	$columns = ['foo','bar'];
	$values  = ['abc','efg'];
	$db->insert($table,$columns,$values);
	
UPDATE:
  ------
  	$id = 2;
	$table    = 'test';
	$columns  = ['foo','bar'];
	$values   = ['abc','efg'];
	$db->update($table,$columns,$values,$id);
	
DELETE ON ID:
  ------
	$table  = 'test';
	$id 	= 2;
	$db->delete($table,$id);
	
QUERY (direct query, no security):
  ------
	$db = new sql();
	$test = $db->query("SELECT * FROM test");
	echo "<pre>". print_r($test) . "</pre>";

CLOSE DB
  ------
$db->close();
