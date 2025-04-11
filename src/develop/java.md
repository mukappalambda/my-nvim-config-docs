# Setup Java Development Environment

We use [jdtls](https://github.com/eclipse-jdtls/eclipse.jdt.ls) as the language server for java.

To install `jdtls`, refer to [Installation](https://github.com/eclipse-jdtls/eclipse.jdt.ls?tab=readme-ov-file#installation).

After installation, make sure to set the `JDTLS_HOME` environment variable on your machine, and the `jdtls` executable should be under `$JDTLS_HOME/bin`:

```console
$ $JDTLS_HOME/bin/jdtls -h
usage: jdtls [-h] [--validate-java-version] [--no-validate-java-version] [--java-executable JAVA_EXECUTABLE] [--jvm-arg JVM_ARG] [-data DATA]

options:
  -h, --help            show this help message and exit
  --validate-java-version
  --no-validate-java-version
  --java-executable JAVA_EXECUTABLE
                        Path to java executable used to start runtime.
  --jvm-arg JVM_ARG     An additional JVM option (can be used multiple times. Note, use with equal sign. For example: --jvm-arg=-Dlog.level=ALL
  -data DATA
```

Open up a Java project managed by gradle or maven, you should see the Java Language Server is up and running.

In normal mode, you can also type `:LspInfo` to see the language server details.
