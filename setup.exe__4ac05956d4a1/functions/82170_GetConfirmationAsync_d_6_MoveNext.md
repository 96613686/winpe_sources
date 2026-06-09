# <GetConfirmationAsync>d__6::MoveNext

- ea: `0x82170`
- end: `0x82270`
- name: `<GetConfirmationAsync>d__6::MoveNext`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x21820`
- `0x2c390`
- `0x46470`
- `0x4fe70`
- `0x4ff40`
- `0x4ff70`
- `0x501b0`
- `0x82170`

## string_xrefs

- `0x82189`: `RemoveButtonText`
- `0x82193`: `remove`

## pseudocode

```c

```

## disassembly

```asm
0x82170  ldarg.0
0x82171  ldfld    int32 <GetConfirmationAsync>d__6::<>1__state
0x82176  stloc.0
0x82177  ldarg.0
0x82178  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand <GetConfirmationAsync>d__6::<>4__this
0x8217d  stloc.1
0x8217e  ldloc.0
0x8217f  brfalse  loc_8221B
0x82184  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x82189  ldstr    aRemovebuttonte// "RemoveButtonText"
0x8218e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId)
0x82193  ldstr    aRemove// "remove"
0x82198  ldc.i4.1
0x82199  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::.ctor(class Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources resources, string buttonId, [opt] valuetype Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButtonType buttonType)
0x8219e  stloc.3
0x8219f  ldc.i4.2
0x821a0  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x821a5  dup
0x821a6  ldc.i4.0
0x821a7  ldloc.3
0x821a8  stelem.ref
0x821a9  dup
0x821aa  ldc.i4.1
0x821ab  ldc.i4.0
0x821ac  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateCancelButton([opt] bool isDefault)
0x821b1  stelem.ref
0x821b2  stloc.s  4
0x821b4  ldloc.1
0x821b5  ldarg.0
0x821b6  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<string> <GetConfirmationAsync>d__6::components
0x821bb  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::ConstructMessage(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> nodesToBeRemoved)
0x821c0  stloc.s  5
0x821c2  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_RemoveComponentsDialogTitle()
0x821c7  ldloc.s  5
0x821c9  ldloc.s  4
0x821cb  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::DeselectOosPackagePrompt
0x821d0  ldc.i4.0
0x821d1  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x821d6  stloc.s  6
0x821d8  ldloc.1
0x821d9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.RemoveOosCommand::serviceOptions
0x821de  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions::get_ErrorDialogService()
0x821e3  ldloc.s  6
0x821e5  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x821ea  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x821ef  stloc.s  7
0x821f1  ldloca.s 7
0x821f3  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x821f8  brtrue.s loc_82238
0x821fa  ldarg.0
0x821fb  ldc.i4.0
0x821fc  dup
0x821fd  stloc.0
0x821fe  stfld    int32 <GetConfirmationAsync>d__6::<>1__state
0x82203  ldarg.0
0x82204  ldloc.s  7
0x82206  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetConfirmationAsync>d__6::<>u__1
0x8220b  ldarg.0
0x8220c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetConfirmationAsync>d__6::<>t__builder
0x82211  ldloca.s 7
0x82213  ldarg.0
0x82214  call     T0x2B000573
0x82219  leave.s  loc_8226F
0x8221b  ldarg.0
0x8221c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetConfirmationAsync>d__6::<>u__1
0x82221  stloc.s  7
0x82223  ldarg.0
0x82224  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <GetConfirmationAsync>d__6::<>u__1
0x82229  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x8222f  ldarg.0
0x82230  ldc.i4.m1
0x82231  dup
0x82232  stloc.0
0x82233  stfld    int32 <GetConfirmationAsync>d__6::<>1__state
0x82238  ldloca.s 7
0x8223a  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x8223f  stloc.2
0x82240  leave.s  loc_8225B
0x82242  stloc.s  8
0x82244  ldarg.0
0x82245  ldc.i4.s 0xFE
0x82247  stfld    int32 <GetConfirmationAsync>d__6::<>1__state
0x8224c  ldarg.0
0x8224d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetConfirmationAsync>d__6::<>t__builder
0x82252  ldloc.s  8
0x82254  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x82259  leave.s  loc_8226F
0x8225b  ldarg.0
0x8225c  ldc.i4.s 0xFE
0x8225e  stfld    int32 <GetConfirmationAsync>d__6::<>1__state
0x82263  ldarg.0
0x82264  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetConfirmationAsync>d__6::<>t__builder
0x82269  ldloc.2
0x8226a  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x8226f  ret
```
