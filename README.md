<img src="/logo.svg" width="92px"/>

Jacli is command-line-focused package manager,
very similar to
[Npm](https://www.npmjs.com/),
[Rubygems](https://github.com/rubygems/rubygems),
[Pip](https://pypi.org/project/pip/),
[Homebrew](https://brew.sh/),
but for Java.
Say, you have a
[JAR](https://en.wikipedia.org/wiki/JAR_%28file_format%29),
which is supposed to be run like this:

```bash
$ java -jar foo.jar
```

To let your users use your `foo.jar` this way, you have to either make it
["fat"](https://stackoverflow.com/questions/11947037/what-is-an-uber-jar)
or instruct them to download all dependencies and make them
[available](https://stackoverflow.com/questions/34286407/gradle-what-is-the-difference-between-classpath-and-compile-dependencies)
on the
[classpath](https://en.wikipedia.org/wiki/Classpath).
Besides, you have to make sure they have the right version of
the [JVM](https://en.wikipedia.org/wiki/Java_virtual_machine) installed.
It's a hassle.

Instead, you use jacli and let your users do this (say, you are no MacOS
and `org.cqfn:foo` are the coordinates of the JAR in Maven Central):

```bash
$ brew install jacli
$ jacli install org.cqfn:foo
$ foo
```

You can also do `uninstall`, `list`, `check`, and so on. Jacli is checking
the JVM for you, downloading all dependencies, creating the command line
hook at `/usr/local/bin/` and so on. It does everything you need in order
to run this single JAR smoothly.

Jacli uses [Maven](https://maven.apache.org/) under the hood
and respects your [`settings.xml`](https://maven.apache.org/settings.html).

All you need to do in order to make your JAR jacli-ready is to put
`jacli.properties` into its
[`META-INF`](https://docs.oracle.com/javase/7/docs/technotes/guides/jar/jar.html#The_META-INF_directory)
directory:

```ini
binary=foo
jvm.min=8
jvm.max=13
```

The logo is made by [Freepik](https://www.freepik.com).
