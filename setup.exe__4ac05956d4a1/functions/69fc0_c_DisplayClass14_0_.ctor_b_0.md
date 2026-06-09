# <>c__DisplayClass14_0::<.ctor>b__0

- ea: `0x69fc0`
- end: `0x6a026`
- name: `<>c__DisplayClass14_0::<.ctor>b__0`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0xe180`
- `0x19ba0`
- `0x2d6b0`
- `0x2d6c0`
- `0x69fc0`

## string_xrefs

- `0x6a001`: `Executing update command from {0}`
- `0x6a00e`: `UpdateDialogMainPageViewModel`

## pseudocode

```c

```

## disassembly

```asm
0x69fc0  ldarg.0
0x69fc1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass14_0::serviceOptions
0x69fc6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Telemetry()
0x69fcb  ldarg.0
0x69fcc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass14_0::serviceOptions
0x69fd1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x69fd6  ldc.i4.2
0x69fd7  ldc.i4.0
0x69fd8  ldnull
0x69fd9  call     void Microsoft.VisualStudio.Setup.Installer.UiTelemetry::WriteButtonEvent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, valuetype Microsoft.VisualStudio.Setup.Installer.ButtonName buttonName, valuetype Microsoft.VisualStudio.Setup.Installer.UserExecuteAction action, [opt] string message)
0x69fde  ldarg.0
0x69fdf  ldfld    class Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel <>c__DisplayClass14_0::<>4__this
0x69fe4  ldarg.0
0x69fe5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallOperationContextProvider <>c__DisplayClass14_0::contextProvider
0x69fea  call     instance class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext Microsoft.VisualStudio.Setup.Installer.UpdateDialog.ViewModels.UpdateDialogMainPageViewModel::GetOperationContext(class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallOperationContextProvider contextProvider)
0x69fef  stloc.0
0x69ff0  ldarg.0
0x69ff1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.AppInitializerServiceOptions <>c__DisplayClass14_0::serviceOptions
0x69ff6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x69ffb  dup
0x69ffc  brtrue.s loc_6A001
0x69ffe  pop
0x69fff  br.s     loc_6A019
0x6a001  ldstr    aExecutingUpdat// "Executing update command from {0}"
0x6a006  ldc.i4.1
0x6a007  newarr   [mscorlib]System.Object
0x6a00c  dup
0x6a00d  ldc.i4.0
0x6a00e  ldstr    aUpdatedialogma// "UpdateDialogMainPageViewModel"
0x6a013  stelem.ref
0x6a014  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x6a019  ldarg.0
0x6a01a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext> <>c__DisplayClass14_0::updateCommand
0x6a01f  ldloc.0
0x6a020  callvirt instance void class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Installer.OperationContext>::Execute(var<u1>)
0x6a025  ret
```
