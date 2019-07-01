#### Subprocesses with common main process

A RHPAM process illustrating how a common master process can be combined with multiple versions or flavours of a subprocess. This is based on the possibility to import a kjar into another kjar. The assets of the imported kjar become available in the main kjar.

* The project contains a process called `sub-process`. This corresponds to the name of the sub-process imported into the main process.
* The `pom.xml` of the project contains a dependency to the kjar containing the main process.
* The `kmodule.xml` descriptor in `src/main/resources/META-INF` contains a definition of a named _kbase_ and _ksession_. The main process kjar is imported into this kjar by specifying it in the `includes` attribute of the `kbase` element.
* When deployed, the assets defined in the imported kjar are added to this kjar. So it is now possible to create an instance of the main process which includes the `sub-process` as a sub-process.