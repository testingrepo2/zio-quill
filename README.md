[//]: # (This file was autogenerated using `zio-sbt-website` plugin via `sbt generateReadme` command.)
[//]: # (So please do not edit it manually. Instead, change "docs/index.md" file or sbt setting keys)
[//]: # (e.g. "readmeDocumentation" and "readmeSupport".)
<p align="center">
  <img src="https://raw.githubusercontent.com/getquill/quill/master/quill.png">
</p>

# ZIO Quill

Quill provides a Quoted Domain Specific Language ([QDSL](https://homepages.inf.ed.ac.uk/wadler/papers/qdsl/qdsl.pdf)) to express queries in Scala and execute them in a target language. 

[![Production Ready](https://img.shields.io/badge/Project%20Stage-Production%20Ready-brightgreen.svg)](https://github.com/zio/zio/wiki/Project-Stages) ![CI Badge](https://github.com/zio/zio-quill/workflows/CI/badge.svg) [![Sonatype Releases](https://img.shields.io/nexus/r/https/oss.sonatype.org/io.getquill/quill-core_2.12.svg?label=Sonatype%20Release)](https://oss.sonatype.org/content/repositories/releases/io/getquill/quill-core_2.12/) [![Sonatype Snapshots](https://img.shields.io/nexus/s/https/oss.sonatype.org/io.getquill/quill-core_2.12.svg?label=Sonatype%20Snapshot)](https://oss.sonatype.org/content/repositories/snapshots/io/getquill/quill-core_2.12/) [![javadoc](https://javadoc.io/badge2/io.getquill/zio-quill-docs_2.12/javadoc.svg)](https://javadoc.io/doc/io.getquill/zio-quill-docs_2.12) [![ZIO Quill](https://img.shields.io/github/stars/zio/zio-quill?style=social)](https://github.com/zio/zio-quill)

## Introduction

The library's core is designed to support multiple target languages, currently featuring specializations for Structured Query Language ([SQL](https://en.wikipedia.org/wiki/SQL)) and Cassandra Query Language ([CQL](https://cassandra.apache.org/doc/latest/cql/)).

1. **Boilerplate-free mapping**: The database schema is mapped using simple case classes.
2. **Quoted DSL**: Queries are defined inside a `quote` block. Quill parses each quoted block of code (quotation) at compile time and translates them to an internal Abstract Syntax Tree (AST)
3. **Compile-time query generation**: The `ctx.run` call reads the quotation's AST and translates it to the target language at compile time, emitting the query string as a compilation message. As the query string is known at compile time, the runtime overhead is very low and similar to using the database driver directly.
4. **Compile-time query validation**: If configured, the query is verified against the database at compile time and the compilation fails if it is not valid. The query validation **does not** alter the database state. 

> ### Scala 3 Support
> [ProtoQuill](https://github.com/zio/zio-protoquill) provides Scala 3 support for Quill rebuilding on top of new metaprogramming capabilities from the ground > up! It is published to maven-central as the `quill-<module>_3` line of artifacts.

> ### Doobie Support
> See [here](contexts.md#quill-doobie) for Doobie integration instructions.

## Example

![example](https://raw.githubusercontent.com/getquill/quill/master/example.gif)

Note: The GIF example uses Eclipse, which shows compilation messages to the user.

## Documentation

Learn more on the [ZIO Quill homepage](https://zio.dev/zio-quill)!

## Contributing

For the general guidelines, see ZIO [contributor's guide](https://zio.dev/about/contributing).

## Code of Conduct

See the [Code of Conduct](https://zio.dev/about/code-of-conduct)

## Support

Come chat with us on [![Badge-Discord]][Link-Discord].

[Badge-Discord]: https://img.shields.io/discord/629491597070827530?logo=discord "chat on discord"
[Link-Discord]: https://discord.gg/2ccFBr4 "Discord"

## Maintainers

- @deusaquilus (lead maintainer)
- @fwbrasil (creator)
- @jilen
- @juliano
- @mentegy
- @mdedetrich

### Former maintainers:

- @gustavoamigo
- @godenji
- @lvicentesanchez
- @mxl

You can notify all current maintainers using the handle `@getquill/maintainers`.

## Acknowledgement

The project was created having Philip Wadler's talk ["A practical theory of language-integrated query"](https://www.infoq.com/presentations/theory-language-integrated-query) as its initial inspiration. The development was heavily influenced by the following papers:

* [A Practical Theory of Language-Integrated Query](https://homepages.inf.ed.ac.uk/slindley/papers/practical-theory-of-linq.pdf)
* [Everything old is new again: Quoted Domain Specific Languages](https://homepages.inf.ed.ac.uk/wadler/papers/qdsl/qdsl.pdf)
* [The Flatter, the Better](https://db.inf.uni-tuebingen.de/staticfiles/publications/the-flatter-the-better.pdf)

## License

[License](LICENSE)
