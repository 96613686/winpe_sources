# <<GetExportCommand>b__0>d::MoveNext

- ea: `0x91430`
- end: `0x91753`
- name: `<<GetExportCommand>b__0>d::MoveNext`
- size: `803`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x9c40`
- `0x10bd0`
- `0x21820`
- `0x2c390`
- `0x2d6b0`
- `0x3b660`
- `0x443b0`
- `0x44570`
- `0x4ff10`
- `0x501b0`
- `0x501d0`
- `0x54080`
- `0x55080`
- `0x7fc80`
- `0x91430`

## string_xrefs

- `0x9148e`: `ExportInstallationDetailsProvider`
- `0x91631`: `Failed to export installation configuration to {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x91430  ldarg.0
0x91431  ldfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x91436  stloc.0
0x91437  ldarg.0
0x91438  ldfld    class <>c__DisplayClass23_0 <<GetExportCommand>b__0>d::<>4__this
0x9143d  stloc.1
0x9143e  ldloc.0
0x9143f  ldc.i4.1
0x91440  ble.un.s loc_9147D
0x91442  ldloc.0
0x91443  ldc.i4.2
0x91444  beq      loc_916F8
0x91449  ldarg.0
0x9144a  newobj   instance void <>c__DisplayClass23_1::.ctor()
0x9144f  stfld    class <>c__DisplayClass23_1 <<GetExportCommand>b__0>d::<>8__1
0x91454  ldarg.0
0x91455  ldfld    class <>c__DisplayClass23_1 <<GetExportCommand>b__0>d::<>8__1
0x9145a  ldloc.1
0x9145b  stfld    class <>c__DisplayClass23_0 <>c__DisplayClass23_1::CS$<>8__locals1
0x91460  ldarg.0
0x91461  ldfld    class <>c__DisplayClass23_1 <<GetExportCommand>b__0>d::<>8__1
0x91466  ldloc.1
0x91467  ldfld    class Microsoft.VisualStudio.Setup.Installer.ViewModels.IDirectoryPickerViewModel <>c__DisplayClass23_0::directoryPicker
0x9146c  callvirt instance string Microsoft.VisualStudio.Setup.Installer.ViewModels.IDirectoryPickerViewModel::get_Text()
0x91471  stfld    string <>c__DisplayClass23_1::exportPath
0x91476  ldarg.0
0x91477  ldc.i4.0
0x91478  stfld    int32 <<GetExportCommand>b__0>d::<>7__wrap2
0x9147d  nop
0x9147e  ldloc.0
0x9147f  brfalse.s loc_914FC
0x91481  ldloc.0
0x91482  ldc.i4.1
0x91483  beq      loc_915C2
0x91488  ldloc.1
0x91489  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider <>c__DisplayClass23_0::<>4__this
0x9148e  ldstr    aExportinstalla// "ExportInstallationDetailsProvider"
0x91493  call     instance void Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider::EndOperationWithSuccess([opt] string message)
0x91498  ldloc.1
0x91499  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider <>c__DisplayClass23_0::<>4__this
0x9149e  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider::closeCommand
0x914a3  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand::Execute()
0x914a8  ldloc.1
0x914a9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel <>c__DisplayClass23_0::product
0x914ae  ldarg.0
0x914af  ldfld    class <>c__DisplayClass23_1 <<GetExportCommand>b__0>d::<>8__1
0x914b4  ldfld    string <>c__DisplayClass23_1::exportPath
0x914b9  ldloca.s 9
0x914bb  initobj  [mscorlib]System.Threading.CancellationToken
0x914c1  ldloc.s  9
0x914c3  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel::ExportSelectionsAsync(string filePath, [opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x914c8  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetAwaiter()
0x914cd  stloc.s  8
0x914cf  ldloca.s 8
0x914d1  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::get_IsCompleted()
0x914d6  brtrue.s loc_91519
0x914d8  ldarg.0
0x914d9  ldc.i4.0
0x914da  dup
0x914db  stloc.0
0x914dc  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x914e1  ldarg.0
0x914e2  ldloc.s  8
0x914e4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <<GetExportCommand>b__0>d::<>u__1
0x914e9  ldarg.0
0x914ea  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <<GetExportCommand>b__0>d::<>t__builder
0x914ef  ldloca.s 8
0x914f1  ldarg.0
0x914f2  call     T0x2B000614
0x914f7  leave    loc_91752
0x914fc  ldarg.0
0x914fd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <<GetExportCommand>b__0>d::<>u__1
0x91502  stloc.s  8
0x91504  ldarg.0
0x91505  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>> <<GetExportCommand>b__0>d::<>u__1
0x9150a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>
0x91510  ldarg.0
0x91511  ldc.i4.m1
0x91512  dup
0x91513  stloc.0
0x91514  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x91519  ldloca.s 8
0x9151b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<string>>::GetResult()
0x91520  stloc.2
0x91521  ldsfld   string [mscorlib]System.String::Empty
0x91526  stloc.3
0x91527  ldloc.1
0x91528  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider <>c__DisplayClass23_0::<>4__this
0x9152d  ldloc.2
0x9152e  call     instance string Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider::GetExportResultMessage(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> failedPackages)
0x91533  stloc.s  4
0x91535  ldc.i4.1
0x91536  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x9153b  dup
0x9153c  ldc.i4.0
0x9153d  ldc.i4.1
0x9153e  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateOkButton([opt] bool isDefault)
0x91543  stelem.ref
0x91544  stloc.s  5
0x91546  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_OpenFolderLinkText()
0x9154b  stloc.s  6
0x9154d  ldarg.0
0x9154e  ldfld    class <>c__DisplayClass23_1 <<GetExportCommand>b__0>d::<>8__1
0x91553  ldftn    instance void <>c__DisplayClass23_1::<GetExportCommand>b__1()
0x91559  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x9155e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x91563  stloc.s  7
0x91565  ldloc.1
0x91566  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider <>c__DisplayClass23_0::<>4__this
0x9156b  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider::serviceOptions
0x91570  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions::get_ErrorDialogService()
0x91575  ldloc.3
0x91576  ldloc.s  4
0x91578  ldloc.s  5
0x9157a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ExportConfigSucceeded
0x9157f  ldloc.s  6
0x91581  ldloc.s  7
0x91583  ldc.i4.0
0x91584  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, string customLinkText, class [System]System.Windows.Input.ICommand customLinkCommand, [opt] bool showTroubleshootingTipsLink)
0x91589  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x9158e  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x91593  stloc.s  0xA
0x91595  ldloca.s 0xA
0x91597  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x9159c  brtrue.s loc_915DF
0x9159e  ldarg.0
0x9159f  ldc.i4.1
0x915a0  dup
0x915a1  stloc.0
0x915a2  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x915a7  ldarg.0
0x915a8  ldloc.s  0xA
0x915aa  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<GetExportCommand>b__0>d::<>u__2
0x915af  ldarg.0
0x915b0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <<GetExportCommand>b__0>d::<>t__builder
0x915b5  ldloca.s 0xA
0x915b7  ldarg.0
0x915b8  call     T0x2B000615
0x915bd  leave    loc_91752
0x915c2  ldarg.0
0x915c3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<GetExportCommand>b__0>d::<>u__2
0x915c8  stloc.s  0xA
0x915ca  ldarg.0
0x915cb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<GetExportCommand>b__0>d::<>u__2
0x915d0  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x915d6  ldarg.0
0x915d7  ldc.i4.m1
0x915d8  dup
0x915d9  stloc.0
0x915da  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x915df  ldloca.s 0xA
0x915e1  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x915e6  pop
0x915e7  leave.s  loc_915FC
0x915e9  stloc.s  0xB
0x915eb  ldarg.0
0x915ec  ldloc.s  0xB
0x915ee  stfld    object <<GetExportCommand>b__0>d::<>7__wrap1
0x915f3  ldarg.0
0x915f4  ldc.i4.1
0x915f5  stfld    int32 <<GetExportCommand>b__0>d::<>7__wrap2
0x915fa  leave.s  loc_915FC
0x915fc  ldarg.0
0x915fd  ldfld    int32 <<GetExportCommand>b__0>d::<>7__wrap2
0x91602  stloc.s  0xC
0x91604  ldloc.s  0xC
0x91606  ldc.i4.1
0x91607  bne.un   loc_9171D
0x9160c  ldarg.0
0x9160d  ldfld    object <<GetExportCommand>b__0>d::<>7__wrap1
0x91612  castclass [mscorlib]System.Exception
0x91617  stloc.s  0xD
0x91619  ldloc.1
0x9161a  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider <>c__DisplayClass23_0::<>4__this
0x9161f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider::serviceOptions
0x91624  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x91629  dup
0x9162a  brtrue.s loc_9162F
0x9162c  pop
0x9162d  br.s     loc_91659
0x9162f  ldloc.s  0xD
0x91631  ldstr    aFailedToExport_1// "Failed to export installation configura"...
0x91636  ldc.i4.2
0x91637  newarr   [mscorlib]System.Object
0x9163c  dup
0x9163d  ldc.i4.0
0x9163e  ldarg.0
0x9163f  ldfld    class <>c__DisplayClass23_1 <<GetExportCommand>b__0>d::<>8__1
0x91644  ldfld    string <>c__DisplayClass23_1::exportPath
0x91649  stelem.ref
0x9164a  dup
0x9164b  ldc.i4.1
0x9164c  ldloc.s  0xD
0x9164e  callvirt instance string [mscorlib]System.Object::ToString()
0x91653  stelem.ref
0x91654  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x91659  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ExportFailedTitle()
0x9165e  stloc.s  0xE
0x91660  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ExportFailedMessage()
0x91665  stloc.s  0xF
0x91667  ldc.i4.1
0x91668  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x9166d  dup
0x9166e  ldc.i4.0
0x9166f  ldc.i4.1
0x91670  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateOkButton([opt] bool isDefault)
0x91675  stelem.ref
0x91676  stloc.s  0x10
0x91678  ldloc.s  0xD
0x9167a  isinst   [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.LocalizedException
0x9167f  stloc.s  0x11
0x91681  ldloc.s  0x11
0x91683  brfalse.s loc_916A1
0x91685  ldc.i4.2
0x91686  newarr   [mscorlib]System.String
0x9168b  dup
0x9168c  ldc.i4.0
0x9168d  ldloc.s  0xF
0x9168f  stelem.ref
0x91690  dup
0x91691  ldc.i4.1
0x91692  ldloc.s  0x11
0x91694  callvirt instance string [mscorlib]System.Exception::get_Message()
0x91699  stelem.ref
0x9169a  call     string Microsoft.VisualStudio.Setup.Installer.CommonUtilities::CreateMultiLineErrorMessage(string[] messages)
0x9169f  stloc.s  0xF
0x916a1  ldloc.1
0x916a2  ldfld    class Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider <>c__DisplayClass23_0::<>4__this
0x916a7  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.InstallationDetails.ExportInstallationDetailsProvider::serviceOptions
0x916ac  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallationDetailsServiceOptions::get_ErrorDialogService()
0x916b1  ldloc.s  0xE
0x916b3  ldloc.s  0xF
0x916b5  ldloc.s  0x10
0x916b7  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::ExportConfigFailed
0x916bc  ldc.i4.0
0x916bd  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x916c2  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x916c7  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x916cc  stloc.s  0xA
0x916ce  ldloca.s 0xA
0x916d0  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x916d5  brtrue.s loc_91715
0x916d7  ldarg.0
0x916d8  ldc.i4.2
0x916d9  dup
0x916da  stloc.0
0x916db  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x916e0  ldarg.0
0x916e1  ldloc.s  0xA
0x916e3  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<GetExportCommand>b__0>d::<>u__2
0x916e8  ldarg.0
0x916e9  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <<GetExportCommand>b__0>d::<>t__builder
0x916ee  ldloca.s 0xA
0x916f0  ldarg.0
0x916f1  call     T0x2B000615
0x916f6  leave.s  loc_91752
0x916f8  ldarg.0
0x916f9  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<GetExportCommand>b__0>d::<>u__2
0x916fe  stloc.s  0xA
0x91700  ldarg.0
0x91701  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <<GetExportCommand>b__0>d::<>u__2
0x91706  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x9170c  ldarg.0
0x9170d  ldc.i4.m1
0x9170e  dup
0x9170f  stloc.0
0x91710  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x91715  ldloca.s 0xA
0x91717  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x9171c  pop
0x9171d  ldarg.0
0x9171e  ldnull
0x9171f  stfld    object <<GetExportCommand>b__0>d::<>7__wrap1
0x91724  leave.s  loc_9173F
0x91726  stloc.s  0x12
0x91728  ldarg.0
0x91729  ldc.i4.s 0xFE
0x9172b  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x91730  ldarg.0
0x91731  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <<GetExportCommand>b__0>d::<>t__builder
0x91736  ldloc.s  0x12
0x91738  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetException(class [mscorlib]System.Exception)
0x9173d  leave.s  loc_91752
0x9173f  ldarg.0
0x91740  ldc.i4.s 0xFE
0x91742  stfld    int32 <<GetExportCommand>b__0>d::<>1__state
0x91747  ldarg.0
0x91748  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder <<GetExportCommand>b__0>d::<>t__builder
0x9174d  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncVoidMethodBuilder::SetResult()
0x91752  ret
```
