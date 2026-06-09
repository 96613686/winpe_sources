# Microsoft.VisualStudio.Setup.Installer.Commands.RestartCommand::.ctor

- ea: `0x55360`
- end: `0x55379`
- name: `Microsoft.VisualStudio.Setup.Installer.Commands.RestartCommand::.ctor`
- size: `25`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x12b30`
- `0x12e00`
- `0x13040`
- `0x1e380`
- `0x5f140`

## callees

- `0x53aa0`

## string_xrefs

- `0x55367`: `serviceOptions`

## pseudocode

```c

```

## disassembly

```asm
0x55360  ldarg.0
0x55361  call     instance void Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase::.ctor()
0x55366  ldarg.1
0x55367  ldstr    aServiceoptions// "serviceOptions"
0x5536c  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x55371  ldarg.0
0x55372  ldarg.1
0x55373  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.RestartCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.RestartCommand::serviceOptions
0x55378  ret
```
