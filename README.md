# class.DB
Minimal PHP database class.

A minimal and lean PHP mysqli database class. 256 lines of code.

Examples of use:

SELECT:
  ------
	$db = new sql();
	$table    = 'test';
	$column   = 'id';
	$value    =  1;
	$operator = '*';
	
	$test = $db->select($table,$operator,$column,$value);
	// becomes: select * from test where id = 1
    	echo "<pre>". print_r($test) . "</pre>";
	$db->close();
	
QUERY (direct query, no security):
  ------
	$db = new sql();
	$test = $db->query("SELECT * FROM test");
	echo "<pre>". print_r($test) . "</pre>";
	$db->close();
	
INSERT:
  ------ 
	$db = new sql();
	$table   = 'test';
	$columns = ['foo','bar'];
	$values  = ['abc','efg'];
	$db->insert($table,$columns,$values);
	$db->close();
	
UPDATE:
  ------
	$db = new sql();
	$table    = 'test';
	$columns  = ['foo','bar'];
	$values   = ['abc','efg'];
	$id = 2;
	$db->update($table,$columns,$values,$id);
	$db->close();
	
DELETE ON ID:
  ------
	$db = new sql();
	$table  = 'test';
	$id 	= 2;
	$db->delete($table,$id);
	$db->close();
	
