# pg-diff
PostgreSQL schema and data comparing tool

Original project from:
[Documentation is here](https://michaelsogos.github.io/pg-diff/)


## For this project use this version of Api:
[https://github.com/ellorenz2/pg-diff-api]


## Added features:

* new config parameter for insert generation "conflictManagmentPolicy" for data insetion
* values could be "", "NOTHING" or "UPDATE"
    * "" : not add anything at insert script like old version
    * "NOTHING": add after insert "ON CONFLICT ({list of key filed setted in config}) DO NOTHING"
   * "UPDATE": add after insert "ON CONFLICT ({list of key filed setted in config}) DO UPDATE SET {field} = EXCLUDED.{field},..." 


### Example:
```json

				"tables": [
					{
						"tableName": "test_generic",
						"tableSchema": "public",
						"tableKeyFields": [
							"id"
						],
						"conflictManagmentPolicy":""
					}
				]
			}
```
