# 13colonies
Logger and Dashboard for Working the 13 Colonies Special Event

## Pi SQLITE Configuration

This flow requires sqlite3 to be installed on your system.  At a terminal command prompt issue the command.  This will load sqlite3 on your Pi.

```
sudo apt-get install sqlite3
```

At the terminal command prompt User (pi) type the following to create a database named qsos and drop you into the database server.

```
sqlite3 qsos
```

Now we need to create some tables within the qsos database.

At the database prompt, copy everything below and paste it into the database.  When done, hit *enter*.  This will create a table named qsos and a table named spots.  It will also create an index on the table qsos.

```
CREATE TABLE IF NOT EXISTS qsos(
  "timestamp" TEXT,
  "band" TEXT,
  "mode" TEXT,
  "call" TEXT
);
```
  
To verify, type .schema at the database carrot prompt to confirm your database structure.  You should see everything above.

```
.schema
```
  
Type .exit to exit out of the database and return to the Pi terminal command prompt.

```
.exit 
```
Your Node Red local qsos database is now created and ready to go.

## Loading Node Dependencies

As of March 2022 the following node dependencies are needed.  Be sure to read the **Configuration** section below.

```

node-red-node-sqlite
node-red-node-irc
```

After installing these node dependencies (which you should receive a pop up message asking you to resolve node dependencies after you clone the project), you'll need to restart Node Red for the nodes to work properly.  From a command prompt, issue the following command.  Note : some dashboard nodes will only populate in your node palette after a restart. 

```sudo systemctl restart nodered.service```

