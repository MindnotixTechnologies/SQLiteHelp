SQLiteHelp
================

A library to allow easy integration of the SQLite database and excel integration to Android applications.

This library enables the user to integrate the SQLite database by creating the objects easily.
Also helps to integrate excel files with the databases directly. 


================

This library uses jxl library for excel handling.
To be able to use the excel imports and exports please add the jxl jar file from the libs folder to your project.


================

HOW TO USE

Add the sqlitehelp.jar file and the jxl.jar present in the libs folder files to your project.
The following code snippet shows how to create a table and insert and retrieve an object from the database :

		SQLiteHelper sHelp = new SQLiteHelper(this, <DATABASE NAME>);
		ArrayList<String> cols = new ArrayList<String>();
		cols.add("A");
		cols.add("B");
		cols.add("C");
		HashMap<String, String> typeMap = new HashMap<String, String>();
		typeMap.put("A", "text primary key");
		typeMap.put("B", "integer");
		typeMap.put("C", "text");
		sHelp.createTable("Table1", cols, typeMap);
		ContentValues values = new ContentValues();
		values.put("A", "AasBC");
		values.put("B", 12);
		values.put("C", "BsCC");
		sHelp.insertSingleEntry("Table1", values);
		ContentValues values2 = sHelp.retrieveSingleEntry("Table1", " A = 'AasBC' ", sHelp.retrieveAllColumnNames("Table1"));
		sHelp.close();
		Toast.makeText(this, values2.getAsString("A")+" "+values2.getAsInteger("B")+" "+values2.getAsString("C")+" ", Toast.LENGTH_LONG).show();

		
		
		
There are various other features that can be used.





//TODO
Create a sample application to show all the aspects of the library.
