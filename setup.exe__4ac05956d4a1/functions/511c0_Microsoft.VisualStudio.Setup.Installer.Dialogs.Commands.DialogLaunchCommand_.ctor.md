# Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogLaunchCommand::.ctor

- ea: `0x511c0`
- end: `0x511eb`
- name: `Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogLaunchCommand::.ctor`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x13040`

## string_xrefs

- `0x511c7`: `serviceOptions`
- `0x511d2`: `launchCommand`

## pseudocode

```c

```

## disassembly

```asm
0x511c0  ldarg.0
0x511c1  call     instance void class Microsoft.VisualStudio.Setup.Installer.Commands.CommandHandlerBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel>::.ctor()
0x511c6  ldarg.1
0x511c7  ldstr    aServiceoptions// "serviceOptions"
0x511cc  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x511d1  ldarg.2
0x511d2  ldstr    aLaunchcommand// "launchCommand"
0x511d7  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x511dc  ldarg.0
0x511dd  ldarg.1
0x511de  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchPageViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogLaunchCommand::serviceOptions
0x511e3  ldarg.0
0x511e4  ldarg.2
0x511e5  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel> Microsoft.VisualStudio.Setup.Installer.Dialogs.Commands.DialogLaunchCommand::launchCommand
0x511ea  ret
```
