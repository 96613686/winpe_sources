# Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::ShowOperationErrorDialog

- ea: `0x24770`
- end: `0x24926`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::ShowOperationErrorDialog`
- size: `438`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xa870`
- `0xcd40`
- `0x217e0`
- `0x21820`
- `0x225e0`
- `0x24770`
- `0x2cb80`
- `0x2cc00`
- `0x2cc10`
- `0x2cc20`
- `0x2cc30`
- `0x34d50`
- `0x4ff10`
- `0x501b0`
- `0x501d0`
- `0x54b60`
- `0x55080`
- `0x6faf0`

## string_xrefs

- `0x24867`: `OperationErrorDialogService: Showing error dialog for localized message`
- `0x248bf`: `OperationErrorDialogService: Showing package dialog for instance: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x24770  ldarg.1
0x24771  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_IsCanceled()
0x24776  brfalse.s loc_2477E
0x24778  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::get_CompletedTask()
0x2477d  ret
0x2477e  ldarg.1
0x2477f  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_Error()
0x24784  stloc.0
0x24785  ldloc.0
0x24786  brtrue.s loc_2478B
0x24788  ldnull
0x24789  br.s     loc_24791
0x2478b  ldloc.0
0x2478c  call     instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::get_LocalizedMessage()
0x24791  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24796  brtrue   loc_24889
0x2479b  ldloc.0
0x2479c  brtrue.s loc_247A1
0x2479e  ldnull
0x2479f  br.s     loc_247A7
0x247a1  ldloc.0
0x247a2  call     instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::get_ErrorName()
0x247a7  ldstr    aPackagefailure// "PackageFailureException"
0x247ac  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x247b1  brfalse  loc_24889
0x247b6  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_SomethingWentWrongTitle()
0x247bb  stloc.s  4
0x247bd  ldloc.0
0x247be  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::get_LocalizedMessage()
0x247c3  stloc.s  5
0x247c5  ldloc.0
0x247c6  call     string Microsoft.VisualStudio.Setup.Installer.Extensions::GetErrorName(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation errorInformation)
0x247cb  stloc.s  6
0x247cd  ldc.i4.1
0x247ce  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x247d3  dup
0x247d4  ldc.i4.0
0x247d5  ldc.i4.1
0x247d6  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateOkButton([opt] bool isDefault)
0x247db  stelem.ref
0x247dc  stloc.s  7
0x247de  ldloc.s  4
0x247e0  ldloc.s  5
0x247e2  ldloc.s  7
0x247e4  ldloc.s  6
0x247e6  ldc.i4.1
0x247e7  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x247ec  stloc.s  8
0x247ee  ldloc.0
0x247ef  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::get_ErrorLogPath()
0x247f4  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x247f9  brtrue.s loc_24856
0x247fb  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x24800  ldarg.0
0x24801  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::serviceOptions
0x24806  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x2480b  stloc.s  9
0x2480d  dup
0x2480e  ldloc.s  9
0x24810  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions serviceOptions)
0x24815  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand <>c__DisplayClass2_0::openUrlCommand
0x2481a  dup
0x2481b  ldloc.0
0x2481c  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.ErrorInformation::get_ErrorLogPath()
0x24821  ldnull
0x24822  ldnull
0x24823  newobj   instance void Microsoft.VisualStudio.Setup.Installer.RichUri::.ctor(string path, [opt] string innerText, [opt] string linkId)
0x24828  stfld    class Microsoft.VisualStudio.Setup.Installer.RichUri <>c__DisplayClass2_0::logUri
0x2482d  ldftn    instance void <>c__DisplayClass2_0::<ShowOperationErrorDialog>b__0()
0x24833  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x24838  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x2483d  stloc.s  0xA
0x2483f  ldloc.s  4
0x24841  ldloc.s  5
0x24843  ldloc.s  7
0x24845  ldloc.s  6
0x24847  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ViewLogsLabel()
0x2484c  ldloc.s  0xA
0x2484e  ldc.i4.1
0x2484f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, string customLinkText, class [System]System.Windows.Input.ICommand customLinkCommand, [opt] bool showTroubleshootingTipsLink)
0x24854  stloc.s  8
0x24856  ldarg.0
0x24857  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::serviceOptions
0x2485c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions::get_Logger()
0x24861  dup
0x24862  brtrue.s loc_24867
0x24864  pop
0x24865  br.s     loc_24876
0x24867  ldstr    aOperationerror// "OperationErrorDialogService: Showing er"...
0x2486c  call     T0x2B000010
0x24871  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x24876  ldarg.0
0x24877  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::serviceOptions
0x2487c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions::get_ErrorDialogService()
0x24881  ldloc.s  8
0x24883  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x24888  ret
0x24889  ldarg.0
0x2488a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::serviceOptions
0x2488f  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDetailInformationReader Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions::get_ErrorDetailInformationReader()
0x24894  ldarg.1
0x24895  callvirt instance class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ErrorDetailInformation Microsoft.VisualStudio.Setup.Installer.Services.IErrorDetailInformationReader::GetPackageErrorMessages(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult)
0x2489a  stloc.s  0xB
0x2489c  ldloc.s  0xB
0x2489e  brfalse.s loc_248EB
0x248a0  ldloc.s  0xB
0x248a2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ViewModels.IErrorDetailViewModel> Microsoft.VisualStudio.Setup.Installer.PackageFailures.ErrorDetailInformation::get_Errors()
0x248a7  call     T0x2B000114
0x248ac  brtrue.s loc_248EB
0x248ae  ldarg.0
0x248af  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::serviceOptions
0x248b4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions::get_Logger()
0x248b9  dup
0x248ba  brtrue.s loc_248BF
0x248bc  pop
0x248bd  br.s     loc_248D8
0x248bf  ldstr    aOperationerror_0// "OperationErrorDialogService: Showing pa"...
0x248c4  ldc.i4.1
0x248c5  newarr   [mscorlib]System.Object
0x248ca  dup
0x248cb  ldc.i4.0
0x248cc  ldarg.1
0x248cd  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.InstallOperationResult::get_InstanceId()
0x248d2  stelem.ref
0x248d3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x248d8  ldarg.0
0x248d9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::serviceOptions
0x248de  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IProblemsDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions::get_ProblemsDialogService()
0x248e3  ldloc.s  0xB
0x248e5  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Services.IProblemsDialogService::ShowProblemsDialog(class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ErrorDetailInformation errorInformation)
0x248ea  ret
0x248eb  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_SomethingWentWrongTitle()
0x248f0  stloc.1
0x248f1  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_GenericInstallOperationFailedMessage()
0x248f6  stloc.2
0x248f7  ldc.i4.1
0x248f8  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x248fd  dup
0x248fe  ldc.i4.0
0x248ff  ldc.i4.1
0x24900  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateOkButton([opt] bool isDefault)
0x24905  stelem.ref
0x24906  stloc.3
0x24907  ldarg.0
0x24908  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.OperationErrorDialogService::serviceOptions
0x2490d  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OperationErrorDialogServiceOptions::get_ErrorDialogService()
0x24912  ldloc.1
0x24913  ldloc.2
0x24914  ldloc.3
0x24915  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::GenericOperationFailureError
0x2491a  ldc.i4.0
0x2491b  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x24920  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x24925  ret
```
