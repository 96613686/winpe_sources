# Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::.cctor

- ea: `0x57650`
- end: `0x57676`
- name: `Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::.cctor`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x57664`: `install`
- `0x57650`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x57650  ldstr    aCache// "cache"
0x57655  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::CachePathKey
0x5765a  ldstr    aShared// "shared"
0x5765f  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::SharedPathKey
0x57664  ldstr    aInstall// "install"
0x57669  stsfld   string Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::InstallPathKey
0x5766e  ldc.i4.s 0x3D
0x57670  stsfld   char Microsoft.VisualStudio.Setup.Installer.CommandLine.PathParser::KeyValueSeparator
0x57675  ret
```
