# class.DB
Minimal PHP database class.

A minimal and lean PHP database class. 256 lines of code.

Examples of use:

  ------
  	SELECT:
	$db = new sql();
	$test = $db->select('test','*','foo','bar');
    		echo "<pre>";
    		print_r($test);
    		echo "</pre>";
	$db->close();
  ------
  	SELECT (direct query, no checks):
	$db = new sql();
	$test = $db->query("SELECT * FROM test");
    		echo "<pre>";
    		print_r($test);
    		echo "</pre>";
	$db->close();
  ------ 
  	INSERT:
	$db = new sql();
	$cols = ['foo','bar'];
	$vals = ['abc','efg'];
	$db->insert('test',$cols,$vals);
	$db->close();
  ------
  	UPDATE:
	$db = new sql();
	$id = 2;
	$cols = ['foo','bar'];
	$vals = ['abc','efg'];
	$db->update('test',$cols,$vals,$id);
	$db->close();
  ------
  	DELETE ON ID:
	$db = new sql();
	$id = 2;
	$db->delete('test',$id);
	$db->close();
	
