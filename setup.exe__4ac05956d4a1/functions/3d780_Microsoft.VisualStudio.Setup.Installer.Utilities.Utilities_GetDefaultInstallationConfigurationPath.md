# Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetDefaultInstallationConfigurationPath

- ea: `0x3d780`
- end: `0x3d7bf`
- name: `Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetDefaultInstallationConfigurationPath`
- size: `63`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x548b0`
- `0x549b0`
- `0x5d220`
- `0x8bdc0`

## callees

- `0x3d780`

## string_xrefs

- `0x3d790`: `.vsconfig`
- `0x3d7b2`: `.vsconfig`
- `0x3d7ad`: `Configs`

## pseudocode

```c

```

## disassembly

```asm
0x3d780  ldarg.0
0x3d781  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_UserDocumentsDirectory()
0x3d786  stloc.0
0x3d787  ldloc.0
0x3d788  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3d78d  brtrue.s loc_3D79D
0x3d78f  ldloc.0
0x3d790  ldstr    aVsconfig// ".vsconfig"
0x3d795  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3d79a  stloc.1
0x3d79b  leave.s  loc_3D7BD
0x3d79d  leave.s  loc_3D7A2
0x3d79f  pop
0x3d7a0  leave.s  loc_3D7A2
0x3d7a2  ldarg.0
0x3d7a3  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_SharedProgramsDirectory()
0x3d7a8  ldstr    aMicrosoftVisua_13// "Microsoft Visual Studio"
0x3d7ad  ldstr    aConfigs// "Configs"
0x3d7b2  ldstr    aVsconfig// ".vsconfig"
0x3d7b7  call     string [mscorlib]System.IO.Path::Combine(string, string, string, string)
0x3d7bc  ret
0x3d7bd  ldloc.1
0x3d7be  ret
```
