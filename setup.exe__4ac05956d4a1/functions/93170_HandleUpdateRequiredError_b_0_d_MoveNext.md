# <<HandleUpdateRequiredError>b__0>d::MoveNext

- ea: `0x93170`
- end: `0x93311`
- name: `<<HandleUpdateRequiredError>b__0>d::MoveNext`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update`

## callees

- `0x21820`
- `0x2c390`
- `0x2d6b0`
- `0x4fe70`
- `0x4ff40`
- `0x4ff70`
- `0x501b0`
- `0x53d50`
- `0x93170`

## string_xrefs

- `0x931dc`: `update`
- `0x9327f`: `update`
- `0x931a2`: `In quiet or passive mode, updating the installer.`
- `0x931d2`: `Update`
- `0x932a1`: `Updating the installer.`

## pseudocode

```c

```

## disassembly

```asm
0x93170  ldarg.0
0x93171  ldfld    int32 <<HandleUpdateRequiredError>b__0>d::<>1__state
0x93176  stloc.0
0x93177  ldarg.0
0x93178  ldfld    class <>c__DisplayClass6_0 <<HandleUpdateRequiredError>b__0>d::<>4__this
0x9317d  stloc.1
0x9317e  ldloc.0
0x9317f  brfalse  loc_9325B
0x93184  ldloc.1
0x93185  ldfld    bool <>c__DisplayClass6_0::quietOrPassive
0x9318a  brfalse.s loc_931C1
0x9318c  ldloc.1
0x9318d  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand <>c__DisplayClass6_0::<>4__this
0x93192  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand::serviceOptions
0x93197  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x9319c  dup
0x9319d  brtrue.s loc_931A2
0x9319f  pop
0x931a0  br.s     loc_931B1
0x931a2  ldstr    aInQuietOrPassi_0// "In quiet or passive mode, updating the "...
0x931a7  call     T0x2B000010
0x931ac  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x931b1  ldloc.1
0x931b2  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand <>c__DisplayClass6_0::<>4__this
0x931b7  call     instance void Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand::InvokeInstallerUpdate()
0x931bc  leave    loc_932FD
0x931c1  ldsfld   string [mscorlib]System.String::Empty
0x931c6  stloc.2
0x931c7  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_InstallerUpdateRequired()
0x931cc  stloc.3
0x931cd  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x931d2  ldstr    aUpdate_0// "Update"
0x931d7  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId)
0x931dc  ldstr    aUpdate// "update"
0x931e1  ldc.i4.1
0x931e2  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::.ctor(class Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources resources, string buttonId, [opt] valuetype Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButtonType buttonType)
0x931e7  stloc.s  4
0x931e9  ldc.i4.2
0x931ea  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x931ef  dup
0x931f0  ldc.i4.0
0x931f1  ldloc.s  4
0x931f3  stelem.ref
0x931f4  dup
0x931f5  ldc.i4.1
0x931f6  ldc.i4.0
0x931f7  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateCancelButton([opt] bool isDefault)
0x931fc  stelem.ref
0x931fd  stloc.s  5
0x931ff  ldloc.2
0x93200  ldloc.3
0x93201  ldloc.s  5
0x93203  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::InstallerUpdateRequired
0x93208  ldc.i4.0
0x93209  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x9320e  stloc.s  6
0x93210  ldloc.1
0x93211  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand <>c__DisplayClass6_0::<>4__this
0x93216  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand::serviceOptions
0x9321b  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions::get_ErrorDialogService()
0x93220  ldloc.s  6
0x93222  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x93227  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x9322c  stloc.s  7
0x9322e  ldloca.s 7
0x93230  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x93235  brtrue.s loc_93278
0x93237  ldarg.0
0x93238  ldc.i4.0
0x93239  dup
0x9323a  stloc.0
0x9323b  stfld    int32 <<HandleUpdateRequiredError>b__0>d::<>1__state
0x93240  ldarg.0
0x93241  ldloc.s  7
0x93243  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<HandleUpdateRequiredError>b__0>d::<>u__1
0x93248  ldarg.0
0x93249  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<HandleUpdateRequiredError>b__0>d::<>t__builder
0x9324e  ldloca.s 7
0x93250  ldarg.0
0x93251  call     T0x2B00062C
0x93256  leave    loc_93310
0x9325b  ldarg.0
0x9325c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<HandleUpdateRequiredError>b__0>d::<>u__1
0x93261  stloc.s  7
0x93263  ldarg.0
0x93264  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<HandleUpdateRequiredError>b__0>d::<>u__1
0x93269  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x9326f  ldarg.0
0x93270  ldc.i4.m1
0x93271  dup
0x93272  stloc.0
0x93273  stfld    int32 <<HandleUpdateRequiredError>b__0>d::<>1__state
0x93278  ldloca.s 7
0x9327a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x9327f  ldstr    aUpdate// "update"
0x93284  callvirt instance bool [mscorlib]System.String::Equals(string)
0x93289  brfalse.s loc_932BD
0x9328b  ldloc.1
0x9328c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand <>c__DisplayClass6_0::<>4__this
0x93291  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand::serviceOptions
0x93296  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x9329b  dup
0x9329c  brtrue.s loc_932A1
0x9329e  pop
0x9329f  br.s     loc_932B0
0x932a1  ldstr    aUpdatingTheIns// "Updating the installer."
0x932a6  call     T0x2B000010
0x932ab  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x932b0  ldloc.1
0x932b1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand <>c__DisplayClass6_0::<>4__this
0x932b6  call     instance void Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand::InvokeInstallerUpdate()
0x932bb  br.s     loc_932E2
0x932bd  ldloc.1
0x932be  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand <>c__DisplayClass6_0::<>4__this
0x932c3  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.InstallDetailsErrorHandlingCommand::serviceOptions
0x932c8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x932cd  dup
0x932ce  brtrue.s loc_932D3
0x932d0  pop
0x932d1  br.s     loc_932E2
0x932d3  ldstr    aUserCanceledCl// "User canceled. Closing the dialog."
0x932d8  call     T0x2B000010
0x932dd  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x932e2  leave.s  loc_932FD
0x932e4  stloc.s  8
0x932e6  ldarg.0
0x932e7  ldc.i4.s 0xFE
0x932e9  stfld    int32 <<HandleUpdateRequiredError>b__0>d::<>1__state
0x932ee  ldarg.0
0x932ef  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<HandleUpdateRequiredError>b__0>d::<>t__builder
0x932f4  ldloc.s  8
0x932f6  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x932fb  leave.s  loc_93310
0x932fd  ldarg.0
0x932fe  ldc.i4.s 0xFE
0x93300  stfld    int32 <<HandleUpdateRequiredError>b__0>d::<>1__state
0x93305  ldarg.0
0x93306  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<HandleUpdateRequiredError>b__0>d::<>t__builder
0x9330b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x93310  ret
```
