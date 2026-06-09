# Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::.ctor

- ea: `0x50660`
- end: `0x506d9`
- name: `Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::.ctor`
- size: `121`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x87150`

## callees

- `0x13b20`
- `0x50660`
- `0x540d0`

## string_xrefs

- `0x50668`: `serviceOptions`
- `0x5067e`: `buttonCommand`

## pseudocode

```c

```

## disassembly

```asm
0x50660  ldarg.0
0x50661  ldarg.1
0x50662  call     instance void Microsoft.VisualStudio.Setup.Installer.ViewModels.ViewModelBase::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions options)
0x50667  ldarg.1
0x50668  ldstr    aServiceoptions// "serviceOptions"
0x5066d  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x50672  ldarg.2
0x50673  ldstr    aButtontext// "buttonText"
0x50678  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x5067d  ldarg.3
0x5067e  ldstr    aButtoncommand// "buttonCommand"
0x50683  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x50688  ldarg.0
0x50689  ldarg.1
0x5068a  stfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.DialogErrorDetailsServiceOptions Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::serviceOptions
0x5068f  ldarg.0
0x50690  ldarg.2
0x50691  stfld    string Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::<ButtonText>k__BackingField
0x50696  ldarg.0
0x50697  ldarg.3
0x50698  callvirt instance class [System]System.Windows.Input.ICommand Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommandBase::get_Command()
0x5069d  stfld    class [System]System.Windows.Input.ICommand Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::<ButtonCommand>k__BackingField
0x506a2  ldarg.0
0x506a3  ldarg.s  5
0x506a5  brtrue.s loc_506AA
0x506a7  ldnull
0x506a8  br.s     loc_506B1
0x506aa  ldarg.s  5
0x506ac  callvirt instance class [System]System.Windows.Input.ICommand Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommandBase::get_Command()
0x506b1  stfld    class [System]System.Windows.Input.ICommand Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::<ProvideFeedbackCommand>k__BackingField
0x506b6  ldarg.0
0x506b7  call     T0x2B000117
0x506bc  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.PackageFailures.ViewModels.IErrorDetailViewModel> Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::errorDetails
0x506c1  ldarg.0
0x506c2  ldarg.s  4
0x506c4  stfld    class Microsoft.VisualStudio.Setup.Installer.FinalErrorResult Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::finalErrorResult
0x506c9  ldarg.0
0x506ca  ldc.i4.1
0x506cb  stfld    bool Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::isLoading
0x506d0  ldarg.0
0x506d1  ldarg.s  6
0x506d3  stfld    int32 Microsoft.VisualStudio.Setup.Installer.Dialogs.ViewModels.DialogErrorDetailsViewModel::<CloseExitCode>k__BackingField
0x506d8  ret
```
