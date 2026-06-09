# Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetInstallationConfigurationFileFilters

- ea: `0x3d7c0`
- end: `0x3d7eb`
- name: `Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetInstallationConfigurationFileFilters`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x5d220`
- `0x7f1d0`
- `0x89930`
- `0x89af0`

## callees

- `0x20f00`

## string_xrefs

- `0x3d7c8`: `VSConfig (*.vsconfig)`
- `0x3d7cd`: `*.vsconfig`
- `0x3d7da`: `JSON (*.json)`
- `0x3d7df`: `*.json`

## pseudocode

```c

```

## disassembly

```asm
0x3d7c0  ldc.i4.2
0x3d7c1  newarr   Microsoft.VisualStudio.Setup.Installer.Services.FileExtensionFilter
0x3d7c6  dup
0x3d7c7  ldc.i4.0
0x3d7c8  ldstr    aVsconfigVsconf// "VSConfig (*.vsconfig)"
0x3d7cd  ldstr    aVsconfig_0// "*.vsconfig"
0x3d7d2  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.FileExtensionFilter::.ctor(string displayText, string filter)
0x3d7d7  stelem.ref
0x3d7d8  dup
0x3d7d9  ldc.i4.1
0x3d7da  ldstr    aJsonJson// "JSON (*.json)"
0x3d7df  ldstr    aJson// "*.json"
0x3d7e4  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.FileExtensionFilter::.ctor(string displayText, string filter)
0x3d7e9  stelem.ref
0x3d7ea  ret
```
