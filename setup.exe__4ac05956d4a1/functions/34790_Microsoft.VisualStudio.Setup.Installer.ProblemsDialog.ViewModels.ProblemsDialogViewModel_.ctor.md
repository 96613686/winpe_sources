# Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::.ctor

- ea: `0x34790`
- end: `0x34891`
- name: `Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::.ctor`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6fb40`

## callees

- `0xcd40`
- `0x13b20`
- `0x2cb80`
- `0x34380`
- `0x34390`
- `0x343a0`
- `0x343b0`
- `0x34790`
- `0x34930`
- `0x34940`
- `0x35010`
- `0x54b60`
- `0x55080`
- `0x767c0`

## string_xrefs

- `0x347af`: `serviceOptions`
- `0x347c5`: `closeButtonCommand`

## pseudocode

```c

```

## disassembly

```asm
0x34790  newobj   instance void <>c__DisplayClass0_0::.ctor()
0x34795  stloc.0
0x34796  ldloc.0
0x34797  ldarg.1
0x34798  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions <>c__DisplayClass0_0::serviceOptions
0x3479d  ldarg.0
0x3479e  ldloc.0
0x3479f  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions <>c__DisplayClass0_0::serviceOptions
0x347a4  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.ViewModelBase::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions options)
0x347a9  ldloc.0
0x347aa  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions <>c__DisplayClass0_0::serviceOptions
0x347af  ldstr    aServiceoptions// "serviceOptions"
0x347b4  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x347b9  ldarg.2
0x347ba  ldstr    aResources// "resources"
0x347bf  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x347c4  ldarg.3
0x347c5  ldstr    aClosebuttoncom// "closeButtonCommand"
0x347ca  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x347cf  ldarg.0
0x347d0  ldarg.2
0x347d1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.IProblemsDialogResources::get_Title()
0x347d6  stfld    string Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<Title>k__BackingField
0x347db  ldarg.0
0x347dc  ldarg.3
0x347dd  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<CloseButtonCommand>k__BackingField
0x347e2  ldarg.0
0x347e3  ldarg.2
0x347e4  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.IProblemsDialogResources::get_ShowTroubleshootingTipsLink()
0x347e9  stfld    bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ShowTroubleshootingTipsLink>k__BackingField
0x347ee  ldarg.0
0x347ef  ldarg.2
0x347f0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ViewModels.IErrorDetailViewModel> Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.IProblemsDialogResources::get_ErrorDetails()
0x347f5  call     T0x2B000114
0x347fa  stfld    bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ShowViewLogsLargeLink>k__BackingField
0x347ff  ldarg.0
0x34800  ldarg.0
0x34801  call     instance bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::get_ShowViewLogsLargeLink()
0x34806  ldc.i4.0
0x34807  ceq
0x34809  stfld    bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ShowViewLogsLink>k__BackingField
0x3480e  ldarg.0
0x3480f  ldarg.0
0x34810  call     instance bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::get_ShowViewLogsLink()
0x34815  stfld    bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ShowProblemDetailList>k__BackingField
0x3481a  ldarg.2
0x3481b  callvirt instance string Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.IProblemsDialogResources::get_ErrorLogPath()
0x34820  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x34825  brtrue.s loc_3486B
0x34827  ldloc.0
0x34828  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions <>c__DisplayClass0_0::serviceOptions
0x3482d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions::.ctor(class [mscorlib]System.IServiceProvider services)
0x34832  stloc.1
0x34833  ldloc.0
0x34834  ldloc.1
0x34835  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions serviceOptions)
0x3483a  stfld    class Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand <>c__DisplayClass0_0::openUrlCommand
0x3483f  ldloc.0
0x34840  ldarg.2
0x34841  callvirt instance string Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.IProblemsDialogResources::get_ErrorLogPath()
0x34846  ldnull
0x34847  ldnull
0x34848  newobj   instance void Microsoft.VisualStudio.Setup.Installer.RichUri::.ctor(string path, [opt] string innerText, [opt] string linkId)
0x3484d  stfld    class Microsoft.VisualStudio.Setup.Installer.RichUri <>c__DisplayClass0_0::logUri
0x34852  ldarg.0
0x34853  ldloc.0
0x34854  ldftn    instance void <>c__DisplayClass0_0::<.ctor>b__0()
0x3485a  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3485f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Commands.RelayCommand::.ctor(class [mscorlib]System.Action execute)
0x34864  stfld    class [System]System.Windows.Input.ICommand Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ViewLogsCommand>k__BackingField
0x34869  br.s     loc_34879
0x3486b  ldarg.0
0x3486c  ldc.i4.0
0x3486d  stfld    bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ShowViewLogsLargeLink>k__BackingField
0x34872  ldarg.0
0x34873  ldc.i4.0
0x34874  stfld    bool Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ShowViewLogsLink>k__BackingField
0x34879  ldarg.0
0x3487a  ldloc.0
0x3487b  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions <>c__DisplayClass0_0::serviceOptions
0x34880  ldarg.2
0x34881  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ViewModels.IErrorDetailViewModel> Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.IProblemsDialogResources::get_ErrorDetails()
0x34886  newobj   instance void Microsoft.VisualStudio.Setup.Installer.PackageFailures.ViewModels.ErrorDetailListViewModel::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions serviceOptions, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ViewModels.IErrorDetailViewModel> errorDetails)
0x3488b  stfld    class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ViewModels.IErrorDetailListViewModel Microsoft.VisualStudio.Setup.Installer.ProblemsDialog.ViewModels.ProblemsDialogViewModel::<ProblemDetailList>k__BackingField
0x34890  ret
```
