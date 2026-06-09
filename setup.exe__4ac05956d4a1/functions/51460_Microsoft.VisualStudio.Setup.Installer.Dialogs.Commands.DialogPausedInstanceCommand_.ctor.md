# Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogPausedInstanceCommand::.ctor

- ea: `0x51460`
- end: `0x5148b`
- name: `Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogPausedInstanceCommand::.ctor`
- size: `43`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x12b30`
- `0x13040`

## callees

- `0x53aa0`

## string_xrefs

- `0x51467`: `serviceOptions`
- `0x51472`: `finalCommand`

## pseudocode

```c

```

## disassembly

```asm
0x51460  ldarg.0
0x51461  call     instance void Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase::.ctor()
0x51466  ldarg.1
0x51467  ldstr    aServiceoptions// "serviceOptions"
0x5146c  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x51471  ldarg.2
0x51472  ldstr    aFinalcommand// "finalCommand"
0x51477  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5147c  ldarg.0
0x5147d  ldarg.1
0x5147e  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.DialogFinalCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogPausedInstanceCommand::serviceOptions
0x51483  ldarg.0
0x51484  ldarg.2
0x51485  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.FinalErrorResult> Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogPausedInstanceCommand::finalCommand
0x5148a  ret
```
