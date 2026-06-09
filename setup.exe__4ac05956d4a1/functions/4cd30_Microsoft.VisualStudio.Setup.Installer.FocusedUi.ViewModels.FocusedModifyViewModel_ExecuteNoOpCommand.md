# Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedModifyViewModel::ExecuteNoOpCommand

- ea: `0x4cd30`
- end: `0x4cd81`
- name: `Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedModifyViewModel::ExecuteNoOpCommand`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x4cc50`
- `0x852e0`

## callees

- `0xe0f0`
- `0x2d6b0`
- `0x2d6c0`
- `0x4cd30`

## string_xrefs

- `0x4cd41`: `No workloads, components, or extensions to select. Executing no-op command.`

## pseudocode

```c

```

## disassembly

```asm
0x4cd30  ldarg.0
0x4cd31  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FocusedViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedModifyViewModel::serviceOptions
0x4cd36  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x4cd3b  dup
0x4cd3c  brtrue.s loc_4CD41
0x4cd3e  pop
0x4cd3f  br.s     loc_4CD50
0x4cd41  ldstr    aNoWorkloadsCom// "No workloads, components, or extensions"...
0x4cd46  call     T0x2B000010
0x4cd4b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x4cd50  ldarg.0
0x4cd51  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FocusedViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedModifyViewModel::serviceOptions
0x4cd56  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Telemetry()
0x4cd5b  ldarg.0
0x4cd5c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.FocusedViewModelServiceOptions Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedModifyViewModel::serviceOptions
0x4cd61  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x4cd66  ldc.i4.s 0xC
0x4cd68  ldc.i4.0
0x4cd69  ldnull
0x4cd6a  call     void Microsoft.VisualStudio.Setup.Installer.UiTelemetry::WritePageEvent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, valuetype Microsoft.VisualStudio.Setup.Installer.PageName pageName, valuetype Microsoft.VisualStudio.Setup.Installer.UserExecuteAction action, [opt] string message)
0x4cd6f  ldarg.0
0x4cd70  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel> Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedModifyViewModel::noOpCommand
0x4cd75  ldarg.0
0x4cd76  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Installer.FocusedUi.ViewModels.FocusedViewModelBase`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductModel>::get_Product()
0x4cd7b  callvirt instance void class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel>::Execute(var<u1>)
0x4cd80  ret
```
