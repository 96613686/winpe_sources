# Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::Handle

- ea: `0x54120`
- end: `0x5424c`
- name: `Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::Handle`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x93a0`
- `0x21820`
- `0x2c980`
- `0x2c9c0`
- `0x2c9d0`
- `0x3aa10`
- `0x4ff10`
- `0x501b0`
- `0x54120`
- `0x54300`
- `0x54400`
- `0x56860`

## string_xrefs

- `0x5413d`: `Product requires a valid LaunchPath to start.`

## pseudocode

```c

```

## disassembly

```asm
0x54120  ldarg.1
0x54121  ldstr    aOptions// "options"
0x54126  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x5412b  ldarg.1
0x5412c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions::get_Product()
0x54131  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel::get_LaunchPath()
0x54136  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5413b  brfalse.s loc_54148
0x5413d  ldstr    aProductRequire// "Product requires a valid LaunchPath to "...
0x54142  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x54147  throw
0x54148  ldarg.0
0x54149  ldarg.1
0x5414a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::CreateTelemetryOperation(class Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions)
0x5414f  stloc.0
0x54150  ldarg.0
0x54151  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.ILaunchProductArgumentsProvider Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::launchProductArgumentsProvider
0x54156  ldarg.1
0x54157  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions::get_Product()
0x5415c  callvirt instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.ILaunchProductArgumentsProvider::GetLaunchArguments(class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel product)
0x54161  stloc.1
0x54162  ldarg.1
0x54163  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions::get_Product()
0x54168  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel::get_LaunchPath()
0x5416d  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x54172  stloc.2
0x54173  ldarg.0
0x54174  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::serviceOptions
0x54179  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions::get_ProcessService()
0x5417e  ldarg.1
0x5417f  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions::get_Product()
0x54184  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel::get_LaunchPath()
0x54189  ldloc.1
0x5418a  ldloc.2
0x5418b  call     bool Microsoft.VisualStudio.Setup.Installer.CommonExtensions::StartUnelevated(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService processService, string path, [opt] string arguments, [opt] string workingDirectory)
0x54190  pop
0x54191  ldloc.0
0x54192  brfalse.s loc_5419F
0x54194  ldloc.0
0x54195  ldstr    aSuccessfullyLa// "Successfully launched the product"
0x5419a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x5419f  leave    loc_5424B
0x541a4  stloc.3
0x541a5  ldarg.0
0x541a6  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::serviceOptions
0x541ab  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions::get_Logger()
0x541b0  dup
0x541b1  brtrue.s loc_541B6
0x541b3  pop
0x541b4  br.s     loc_541D0
0x541b6  ldloc.3
0x541b7  ldstr    aFailedToLaunch_0// "Failed to launch the product: {0}"
0x541bc  ldc.i4.1
0x541bd  newarr   [mscorlib]System.Object
0x541c2  dup
0x541c3  ldc.i4.0
0x541c4  ldloc.3
0x541c5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x541ca  stelem.ref
0x541cb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x541d0  ldloc.0
0x541d1  brfalse.s loc_541E6
0x541d3  ldloc.0
0x541d4  ldloc.3
0x541d5  callvirt instance string [mscorlib]System.Exception::get_Message()
0x541da  ldloc.3
0x541db  ldstr    aFailedToLaunch_1// "Failed to launch the product"
0x541e0  ldc.i4.0
0x541e1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x541e6  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_SomethingWentWrongTitle()
0x541eb  stloc.s  4
0x541ed  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_LaunchErrorMessage_Args1()
0x541f2  ldarg.1
0x541f3  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductOptions::get_Product()
0x541f8  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.ILaunchableProductModel::get_LaunchPath()
0x541fd  call     string [mscorlib]System.String::Format(string, object)
0x54202  stloc.s  5
0x54204  ldc.i4.1
0x54205  newarr   Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton
0x5420a  dup
0x5420b  ldc.i4.0
0x5420c  ldc.i4.1
0x5420d  call     class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton Microsoft.VisualStudio.Setup.Installer.Dialogs.DialogButton::CreateOkButton([opt] bool isDefault)
0x54212  stelem.ref
0x54213  stloc.s  6
0x54215  ldloc.s  4
0x54217  ldloc.s  5
0x54219  ldloc.s  6
0x5421b  ldsfld   string Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorNames::LaunchFailure
0x54220  ldc.i4.1
0x54221  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Dialogs.ErrorDialogResources::.ctor(string title, string message, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Dialogs.IDialogButton> buttons, string recordedName, [opt] bool showTroubleshootingTipsLink)
0x54226  stloc.s  7
0x54228  ldarg.0
0x54229  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.LaunchProductCommand::serviceOptions
0x5422e  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.LaunchProductCommandServiceOptions::get_ErrorService()
0x54233  ldloc.s  7
0x54235  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.VisualStudio.Setup.Installer.Services.IErrorDialogService::ShowError(class Microsoft.VisualStudio.Setup.Installer.Dialogs.IErrorDialogResources resources)
0x5423a  call     void [Microsoft.VisualStudio.Threading]Microsoft.VisualStudio.Threading.TplExtensions::Forget(class [mscorlib]System.Threading.Tasks.Task)
0x5423f  leave.s  loc_5424B
0x54241  ldloc.0
0x54242  brfalse.s loc_5424A
0x54244  ldloc.0
0x54245  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5424a  endfinally
0x5424b  ret
```
