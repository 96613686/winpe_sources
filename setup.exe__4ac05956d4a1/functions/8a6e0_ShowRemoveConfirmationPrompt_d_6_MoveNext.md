# <ShowRemoveConfirmationPrompt>d__6::MoveNext

- ea: `0x8a6e0`
- end: `0x8a80d`
- name: `<ShowRemoveConfirmationPrompt>d__6::MoveNext`
- size: `301`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops`

## callees

- `0x21820`
- `0x2ba20`
- `0x36390`
- `0x36c00`
- `0x4fe70`
- `0x4ff40`
- `0x4ff70`
- `0x501b0`
- `0x8a6e0`

## string_xrefs

- `0x8a730`: `RemoveButtonText`
- `0x8a73a`: `remove`
- `0x8a7d2`: `remove`

## pseudocode

```c

```

## disassembly

```asm
0x8a6e0  ldarg.0
0x8a6e1  ldfld    int32 <ShowRemoveConfirmationPrompt>d__6::<>1__state
0x8a6e6  stloc.0
0x8a6e7  ldarg.0
0x8a6e8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand <ShowRemoveConfirmationPrompt>d__6::<>4__this
0x8a6ed  stloc.1
0x8a6ee  ldloc.0
0x8a6ef  brfalse  loc_8A7AE
0x8a6f4  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_RemoveChannel_Args1()
0x8a6f9  ldarg.0
0x8a6fa  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <ShowRemoveConfirmationPrompt>d__6::channel
0x8a6ff  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.PackageResources Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel::get_Resources()
0x8a704  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.PackageResources::get_Name()
0x8a709  call     string [mscorlib]System.String::Format(string, object)
0x8a70e  stloc.3
0x8a70f  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_RemoveChannelPrompt_Args1()
0x8a714  ldarg.0
0x8a715  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel <ShowRemoveConfirmationPrompt>d__6::channel
0x8a71a  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.PackageResources Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel::get_Resources()
0x8a71f  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.PackageResources::get_Name()
0x8a724  call     string [mscorlib]System.String::Format(string, object)
0x8a729  stloc.s  4
0x8a72b  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x8a730  ldstr    aRemovebuttonte// "RemoveButtonText"
0x8a735  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId)
0x8a73a  ldstr    aRemove// "remove"
0x8a73f  ldc.i4.1
0x8a740  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::.ctor(class Microsoft.VisualStudio.Setup.Installer.Dialogs.ButtonResources resources, string buttonId, [opt] valuetype Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButtonType buttonType)
0x8a745  stloc.s  5
0x8a747  ldc.i4.2
0x8a748  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x8a74d  dup
0x8a74e  ldc.i4.0
0x8a74f  ldloc.s  5
0x8a751  stelem.ref
0x8a752  dup
0x8a753  ldc.i4.1
0x8a754  ldc.i4.0
0x8a755  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateCancelButton([opt] bool isDefault)
0x8a75a  stelem.ref
0x8a75b  stloc.s  6
0x8a75d  ldloc.1
0x8a75e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.RemoveChannelCommand::serviceOptions
0x8a763  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions::get_ErrorDialogService()
0x8a768  ldloc.3
0x8a769  ldloc.s  4
0x8a76b  ldloc.s  6
0x8a76d  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::RemoveChannelClicked
0x8a772  ldc.i4.0
0x8a773  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x8a778  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x8a77d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x8a782  stloc.s  7
0x8a784  ldloca.s 7
0x8a786  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x8a78b  brtrue.s loc_8A7CB
0x8a78d  ldarg.0
0x8a78e  ldc.i4.0
0x8a78f  dup
0x8a790  stloc.0
0x8a791  stfld    int32 <ShowRemoveConfirmationPrompt>d__6::<>1__state
0x8a796  ldarg.0
0x8a797  ldloc.s  7
0x8a799  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ShowRemoveConfirmationPrompt>d__6::<>u__1
0x8a79e  ldarg.0
0x8a79f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ShowRemoveConfirmationPrompt>d__6::<>t__builder
0x8a7a4  ldloca.s 7
0x8a7a6  ldarg.0
0x8a7a7  call     T0x2B0005CD
0x8a7ac  leave.s  loc_8A80C
0x8a7ae  ldarg.0
0x8a7af  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ShowRemoveConfirmationPrompt>d__6::<>u__1
0x8a7b4  stloc.s  7
0x8a7b6  ldarg.0
0x8a7b7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <ShowRemoveConfirmationPrompt>d__6::<>u__1
0x8a7bc  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x8a7c2  ldarg.0
0x8a7c3  ldc.i4.m1
0x8a7c4  dup
0x8a7c5  stloc.0
0x8a7c6  stfld    int32 <ShowRemoveConfirmationPrompt>d__6::<>1__state
0x8a7cb  ldloca.s 7
0x8a7cd  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x8a7d2  ldstr    aRemove// "remove"
0x8a7d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8a7dc  stloc.2
0x8a7dd  leave.s  loc_8A7F8
0x8a7df  stloc.s  8
0x8a7e1  ldarg.0
0x8a7e2  ldc.i4.s 0xFE
0x8a7e4  stfld    int32 <ShowRemoveConfirmationPrompt>d__6::<>1__state
0x8a7e9  ldarg.0
0x8a7ea  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ShowRemoveConfirmationPrompt>d__6::<>t__builder
0x8a7ef  ldloc.s  8
0x8a7f1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x8a7f6  leave.s  loc_8A80C
0x8a7f8  ldarg.0
0x8a7f9  ldc.i4.s 0xFE
0x8a7fb  stfld    int32 <ShowRemoveConfirmationPrompt>d__6::<>1__state
0x8a800  ldarg.0
0x8a801  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <ShowRemoveConfirmationPrompt>d__6::<>t__builder
0x8a806  ldloc.2
0x8a807  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x8a80c  ret
```
