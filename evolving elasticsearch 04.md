## Security

* Now taking security seriously.
* JarHell check, looks for duplicate jars. For removing stale dependencies
* Java Security Manager. Authorization for java code. Now using minimal privileges.
* Modularization of core so that privileges are only granted where needed
* remove java serialization (java security bug)
