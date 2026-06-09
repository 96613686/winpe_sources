# Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::.ctor

- ea: `0x54b60`
- end: `0x54b79`
- name: `Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::.ctor`
- size: `25`
- prototype: ``
- caller_count: `16`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xe910`
- `0x12330`
- `0x1fab0`
- `0x1fd50`
- `0x24770`
- `0x27630`
- `0x34790`
- `0x3d8c0`
- `0x5a680`
- `0x5f410`
- `0x67e20`
- `0x77400`
- `0x80f50`
- `0x84600`
- `0x85890`
- `0x8a520`

## string_xrefs

- `0x54b67`: `serviceOptions`

## pseudocode

```c

```

## disassembly

```asm
0x54b60  ldarg.0
0x54b61  call     instance void class Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase`1<class Microsoft.VisualStudio.Setup.Installer.RichUri>::.ctor()
0x54b66  ldarg.1
0x54b67  ldstr    aServiceoptions// "serviceOptions"
0x54b6c  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x54b71  ldarg.0
0x54b72  ldarg.1
0x54b73  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::serviceOptions
0x54b78  ret
```
