Jacli is command-line-focused package manager for Java. It is very
similar to
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

Instead, you use jacli and let your users do this:

```bash
$ jacli install foo
$ foo
```

That's it.
