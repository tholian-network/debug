
# Alternative Go Debug Library

This is a downstream fork of the go core included [debug](https://github.com/golang/go/tree/master/src/debug)
package, with enhancements to be able to load binaries from the filesystem, modify them, inject shellcode,
and write them to the filesystem again.


# Motivations

Our EDR Agent's defensive and offensive capabilities rely on understanding binaries on a per-symbol
level and on a per-hashtable-entry level, meaning that a lot of malware tries to hide what it does
by obfuscating their symbols, their hashtable entries, or their resources/text sections of the file.

In order to be able to detect these, and in order to be able to patch these malicious entries out,
this library/package was forked from upstream. The general idea is to offer a "somewhat" syntax tree
for binaries with this package, while it obviously won't be on a language-level and rather focus
on the understanding of shellcode and assembler instructions.


# Compatibility

The exported `structs` try to be compatible as much as possible with upstream, meaning it won't change
behavior if there's no changes to those (formerly internal) struct properties.

This package aims to be compatible to the latest stable upstream `go` version tag, with this
currently being version `go1.22.1`.


# Upstream Forks

- [ ] [Binject/debug](https://github.com/Binject/debug) as an initial inspiration (prototype), and this fork aims to be able to be merged by them.
- [ ] [go/src/debug](https://github.com/golang/go/tree/master/src/debug)


# Changes

Changes are document in the [CHANGES.md](./CHANGES.md), and tries to document changes
on a per-file basis, so that future merges with upstream changes are much easier.

Extended functionality by this fork (e.g. new methods on a struct) are all implemented
inside separate files, so that these changes can be preserved and don't result in stupid
unsemantic `git diff`s that don't make sense.


# License

As with the upstream `go` project, this package also is licensed under the [BSD-3 license](./LICENSE),
while changes to this fork are `(c) 2024 Tholian Network`.

