`sbt run` with provided dependencies
====================================

In my spark projects I mark the dependencies to spark itself as `provided`. Reason for this is that
the jar I'm building with [sbt-assembly] doesn't need to contain the spark jars again as they are
already present on my spark cluster. Therefore my `build.sbt` contains lines like these.

```scala
libraryDependencies ++= Seq(
  "org.apache.spark" %% "spark-core" % sparkVersion % "provided",
  "org.apache.spark" %% "spark-sql" % sparkVersion % "provided",
  ...
)
```

I noticed however that `sbt run` stopped working with an `NoClassDefFoundError` like the following.


    [info] Running Main
    [error] Exception in thread "main" java.lang.NoClassDefFoundError: org/apache/spark/sql/SparkSession$
    [error]         at Main$.main(Main.scala:18)


After reading up on the latest [sbt-assembly docs on provided] I added the following lines to my
`build.sbt` that included the provided dependencies back into the classpath.

```scala
run in Compile <<= Defaults.runTask(fullClasspath in Compile, mainClass in (Compile, run), runner in (Compile, run))
runMain in Compile <<= Defaults.runMainTask(fullClasspath in Compile, runner in (Compile, runMain))
```

The second line is there to fix `sbt runMain`.

[sbt-assembly]: https://github.com/sbt/sbt-assembly
[docs]: https://github.com/sbt/sbt-assembly#-provided-configuration
