
# Changes from upstream go/debug

**elf/file.go**

- [x] Added property `File.DynamicTags map[DynTag]uint64`
- [x] Added property `File.ELFHeader32 *Header32`
- [x] Added property `File.ELFHeader64 *Header64`
- [x] Added property `File.Injection []byte`
- [x] Added property `File.InjectionEOF []byte`
- [x] Added property `SectionHeader.Index uint32` for conversion to/from `Section32` and/or `Section64`

**elf/file_exportedsymbols.go**

- [x] Added method `File.ExportedSymbols() ([]Symbol, error)`

**elf/file_bytes.go**

- [x] Added method `File.Bytes() ([]byte, error)`

**elf/file_write.go**

- [x] Added method `File.Write(name string) error`

