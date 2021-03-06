## etl

Project to implement ETL (Extract, Transform and Load) concept with JAVA The idea in a simple way, we want to create processes which allow multiple sub-processes with input (database query, SOAP webservice, RESTful webservice, CSV file or flat files)

## Test

```xml
<?xml version="1.0" encoding="UTF-8"?>
<ETL xsi:noNamespaceSchemaLocation="../xsd/ETL.xsd"
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
	<Declartion>
		<Connections>
			<Connection url="jdbc:sqlite:./Test/ETL.db" id="etl" username=""
				password="" driver="org.sqlite.JDBC" />
		</Connections>
	</Declartion>
	<Process id="proc1">
		<RESTfulWebservice id="r1">
			<URL>http://localhost:8080/Company/api/Employee</URL>
			<Method>GET</Method>
			<Process id="proc1-child1">
				<Database id="d1" connection-id="etl">
					<sql>INSERT INTO Employee(EMP_ID, NAME) VALUES(?r1./Employees/Employee/ID, '?r1./Employees/Employee/Name')</sql>
				</Database>
			</Process>
		</RESTfulWebservice>
	</Process>
</ETL>

```

## Participate

If anyone with JAVA knoweledge would like to participate, please drop me an e-mail with subject 'etl project': ali.mohammad@fcih.net

## TODO

- [x] Add RESTful Webservice.
- [ ] Add SOAP Webservice.
- [ ] Add UI to handle the etl proceess.

## License

```
Copyright 2015-2019 dinus

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
Status API Training Shop Blog About
© 2016 GitHub, Inc. Terms Privacy Security Contact Help
```
