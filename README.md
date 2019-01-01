# class.DB
Minimal PHP database class.

A minimal and lean PHP mysqli database class. 256 lines of code.

Examples of use:

  ------
  	SELECT:
	
	$db = new sql();
	// Example: 
	$test = $db->select('test','*','id',1);
	// Will become this query: SELECT * FROM TEST WHERE ID = 1
    	echo "<pre>";
    		print_r($test);
    	echo "</pre>";
	$db->close();
  ------
  	QUERY (direct query, no security):
	$db = new sql();
	$test = $db->query("SELECT * FROM test");
    	echo "<pre>";
    		print_r($test);
    	echo "</pre>";
	$db->close();
  ------ 
  	INSERT:
	$db = new sql();
	$columns = ['foo','bar'];
	$values = ['abc','efg'];
	$db->insert('test',$columns,$values);
	$db->close();
  ------
  	UPDATE:
	$db = new sql();
	$id = 2;
	$columns = ['foo','bar'];
	$values = ['abc','efg'];
	$db->update('test',$columns,$values,$id);
	$db->close();
  ------
  	DELETE ON ID:
	$db = new sql();
	$id = 2;
	$db->delete('test',$id);
	$db->close();
	
