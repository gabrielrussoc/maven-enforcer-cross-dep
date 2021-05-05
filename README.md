```
$ mvn validate
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Build Order:
[INFO]
[INFO] parent                                                             [pom]
[INFO] B                                                                  [jar]
[INFO] A                                                                  [jar]
[INFO]
[INFO] ------------------------< parent_group:parent >-------------------------
[INFO] Building parent 3.1-SNAPSHOT                                       [1/3]
[INFO] --------------------------------[ pom ]---------------------------------
[INFO]
[INFO] --- maven-enforcer-plugin:3.0.0-M2:enforce (enforce-versions) @ parent ---
[INFO]
[INFO] ---------------------------< parent_group:B >---------------------------
[INFO] Building B 3.1-SNAPSHOT                                            [2/3]
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-enforcer-plugin:3.0.0-M2:enforce (enforce-versions) @ B ---
[INFO]
[INFO] ---------------------------< parent_group:A >---------------------------
[INFO] Building A 3.1-SNAPSHOT                                            [3/3]
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-enforcer-plugin:3.0.0-M2:enforce (enforce-versions) @ A ---
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for parent 3.1-SNAPSHOT:
[INFO]
[INFO] parent ............................................. SUCCESS [  0.297 s]
[INFO] B .................................................. SUCCESS [  0.003 s]
[INFO] A .................................................. FAILURE [  0.006 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.381 s
[INFO] Finished at: 2021-05-05T13:37:51+01:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-enforcer-plugin:3.0.0-M2:enforce (enforce-versions) on project A: Execution enforce-versions of goal org.apache.maven.plugins:maven-enforcer-plugin:3.0.0-M2:enforce failed: org.apache.maven.shared.dependency.graph.DependencyGraphBuilderException: Could not resolve following dependencies: [parent_group:B:jar:3.1-SNAPSHOT (compile)]: Could not resolve dependencies for project parent_group:A:jar:3.1-SNAPSHOT: Could not find artifact parent_group:B:jar:3.1-SNAPSHOT -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/PluginExecutionException
[ERROR]
[ERROR] After correcting the problems, you can resume the build with the command
[ERROR]   mvn <args> -rf :A
```
---
# With install

```
$ mvn install
...
```

```
# gabriel.russo at C02D65HQMD6R in ~/tmp/maven (git:main) [13:38:14]
$ mvn validate
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Build Order:
[INFO]
[INFO] parent                                                             [pom]
[INFO] B                                                                  [jar]
[INFO] A                                                                  [jar]
[INFO]
[INFO] ------------------------< parent_group:parent >-------------------------
[INFO] Building parent 3.1-SNAPSHOT                                       [1/3]
[INFO] --------------------------------[ pom ]---------------------------------
[INFO]
[INFO] --- maven-enforcer-plugin:3.0.0-M2:enforce (enforce-versions) @ parent ---
[INFO]
[INFO] ---------------------------< parent_group:B >---------------------------
[INFO] Building B 3.1-SNAPSHOT                                            [2/3]
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-enforcer-plugin:3.0.0-M2:enforce (enforce-versions) @ B ---
[INFO]
[INFO] ---------------------------< parent_group:A >---------------------------
[INFO] Building A 3.1-SNAPSHOT                                            [3/3]
[INFO] --------------------------------[ jar ]---------------------------------
[INFO]
[INFO] --- maven-enforcer-plugin:3.0.0-M2:enforce (enforce-versions) @ A ---
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for parent 3.1-SNAPSHOT:
[INFO]
[INFO] parent ............................................. SUCCESS [  0.294 s]
[INFO] B .................................................. SUCCESS [  0.003 s]
[INFO] A .................................................. SUCCESS [  0.009 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.377 s
[INFO] Finished at: 2021-05-05T13:38:17+01:00
[INFO] ------------------------------------------------------------------------
```
