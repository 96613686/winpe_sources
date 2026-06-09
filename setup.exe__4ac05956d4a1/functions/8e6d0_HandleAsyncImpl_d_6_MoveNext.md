# <HandleAsyncImpl>d__6::MoveNext

- ea: `0x8e6d0`
- end: `0x8ec75`
- name: `<HandleAsyncImpl>d__6::MoveNext`
- size: `1445`
- prototype: ``
- caller_count: `0`
- callee_count: `47`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xa1d0`
- `0xa540`
- `0xa5c0`
- `0xa8c0`
- `0xace0`
- `0x22ba0`
- `0x27dc0`
- `0x27de0`
- `0x27e00`
- `0x27e20`
- `0x27e40`
- `0x27e60`
- `0x27e80`
- `0x27ea0`
- `0x27ec0`
- `0x27ee0`
- `0x27f00`
- `0x27f10`
- `0x2bb50`
- `0x2bbe0`
- `0x3a7f0`
- `0x3a910`
- `0x3c1b0`
- `0x3cdd0`
- `0x3dc20`
- `0x59260`
- `0x59280`
- `0x59320`
- `0x59340`
- `0x593a0`
- `0x593c0`
- `0x5a280`
- `0x5a2a0`
- `0x5a2e0`
- `0x5a380`
- `0x5a3a0`
- `0x5a460`
- `0x5a680`
- `0x5a750`
- `0x5a7d0`
- `0x5ac10`
- `0x5baa0`
- `0x5bc10`
- `0x5bd00`
- `0x5bda0`
- `0x5be10`
- `0x8e6d0`

## string_xrefs

- `0x8e935`: `Failed to check for updates in {0}: {1}`
- `0x8e942`: `UpdateCommandLineHandler`

## pseudocode

```c

```

## disassembly

```asm
0x8e6d0  ldarg.0
0x8e6d1  ldfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e6d6  stloc.0
0x8e6d7  ldarg.0
0x8e6d8  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler <HandleAsyncImpl>d__6::<>4__this
0x8e6dd  stloc.1
0x8e6de  ldloc.0
0x8e6df  switch   loc_8E776, loc_8E7F4, loc_8E873, loc_8E8B6, loc_8E9A2, loc_8EA2E, loc_8EB89, loc_8EBFD
0x8e704  ldarg.0
0x8e705  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <HandleAsyncImpl>d__6::token
0x8e70a  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x8e70f  ldloc.1
0x8e710  ldarg.0
0x8e711  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e716  ldarg.0
0x8e717  ldflda   class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e71c  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::TryGetInstalledProduct(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions options, [out] class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel& product)
0x8e721  brfalse  loc_8EC22
0x8e726  ldarg.0
0x8e727  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e72c  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsRebootRequired(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product)
0x8e731  brfalse.s loc_8E79E
0x8e733  ldloc.1
0x8e734  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x8e739  ldloc.1
0x8e73a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::rebootCommand
0x8e73f  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::ShowRebootRequiredBlocker(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand rebootCommand)
0x8e744  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8e749  stloc.2
0x8e74a  ldloca.s 2
0x8e74c  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8e751  brtrue.s loc_8E792
0x8e753  ldarg.0
0x8e754  ldc.i4.0
0x8e755  dup
0x8e756  stloc.0
0x8e757  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e75c  ldarg.0
0x8e75d  ldloc.2
0x8e75e  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e763  ldarg.0
0x8e764  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__6::<>t__builder
0x8e769  ldloca.s 2
0x8e76b  ldarg.0
0x8e76c  call     T0x2B0005F9
0x8e771  leave    loc_8EC74
0x8e776  ldarg.0
0x8e777  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e77c  stloc.2
0x8e77d  ldarg.0
0x8e77e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e783  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8e789  ldarg.0
0x8e78a  ldc.i4.m1
0x8e78b  dup
0x8e78c  stloc.0
0x8e78d  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e792  ldloca.s 2
0x8e794  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8e799  leave    loc_8EC5A
0x8e79e  ldarg.0
0x8e79f  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e7a4  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase::get_Continue()
0x8e7a9  brfalse.s loc_8E81C
0x8e7ab  ldloc.1
0x8e7ac  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.IInstallerUpdateContinueHandler Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::continueHandler
0x8e7b1  ldarg.0
0x8e7b2  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e7b7  ldarg.0
0x8e7b8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e7bd  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.IInstallerUpdateContinueHandler::HandleUpdateAsync(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions updateOptions, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel productSummary)
0x8e7c2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8e7c7  stloc.2
0x8e7c8  ldloca.s 2
0x8e7ca  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8e7cf  brtrue.s loc_8E810
0x8e7d1  ldarg.0
0x8e7d2  ldc.i4.1
0x8e7d3  dup
0x8e7d4  stloc.0
0x8e7d5  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e7da  ldarg.0
0x8e7db  ldloc.2
0x8e7dc  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e7e1  ldarg.0
0x8e7e2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__6::<>t__builder
0x8e7e7  ldloca.s 2
0x8e7e9  ldarg.0
0x8e7ea  call     T0x2B0005F9
0x8e7ef  leave    loc_8EC74
0x8e7f4  ldarg.0
0x8e7f5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e7fa  stloc.2
0x8e7fb  ldarg.0
0x8e7fc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e801  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8e807  ldarg.0
0x8e808  ldc.i4.m1
0x8e809  dup
0x8e80a  stloc.0
0x8e80b  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e810  ldloca.s 2
0x8e812  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8e817  leave    loc_8EC5A
0x8e81c  ldarg.0
0x8e81d  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e822  ldarg.0
0x8e823  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e828  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsChannelHop(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions updateOptions, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel product)
0x8e82d  brfalse.s loc_8E89B
0x8e82f  ldloc.1
0x8e830  ldarg.0
0x8e831  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e836  ldarg.0
0x8e837  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e83c  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::HandleChannelHopAsync(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel product, class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions options)
0x8e841  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8e846  stloc.2
0x8e847  ldloca.s 2
0x8e849  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8e84e  brtrue.s loc_8E88F
0x8e850  ldarg.0
0x8e851  ldc.i4.2
0x8e852  dup
0x8e853  stloc.0
0x8e854  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e859  ldarg.0
0x8e85a  ldloc.2
0x8e85b  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e860  ldarg.0
0x8e861  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__6::<>t__builder
0x8e866  ldloca.s 2
0x8e868  ldarg.0
0x8e869  call     T0x2B0005F9
0x8e86e  leave    loc_8EC74
0x8e873  ldarg.0
0x8e874  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e879  stloc.2
0x8e87a  ldarg.0
0x8e87b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e880  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8e886  ldarg.0
0x8e887  ldc.i4.m1
0x8e888  dup
0x8e889  stloc.0
0x8e88a  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e88f  ldloca.s 2
0x8e891  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8e896  leave    loc_8EC5A
0x8e89b  ldarg.0
0x8e89c  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e8a1  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::ShouldCheckForUpdates(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.InstallerOptionsBase options)
0x8e8a6  brfalse  loc_8E958
0x8e8ab  ldarg.0
0x8e8ac  ldflda   valuetype [mscorlib]System.Threading.CancellationToken <HandleAsyncImpl>d__6::token
0x8e8b1  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x8e8b6  nop
0x8e8b7  ldloc.0
0x8e8b8  ldc.i4.3
0x8e8b9  beq.s    loc_8E8FE
0x8e8bb  ldarg.0
0x8e8bc  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e8c1  ldarg.0
0x8e8c2  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <HandleAsyncImpl>d__6::token
0x8e8c7  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel::CheckForUpdates([opt] valuetype [mscorlib]System.Threading.CancellationToken token)
0x8e8cc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8e8d1  stloc.2
0x8e8d2  ldloca.s 2
0x8e8d4  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8e8d9  brtrue.s loc_8E91A
0x8e8db  ldarg.0
0x8e8dc  ldc.i4.3
0x8e8dd  dup
0x8e8de  stloc.0
0x8e8df  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e8e4  ldarg.0
0x8e8e5  ldloc.2
0x8e8e6  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e8eb  ldarg.0
0x8e8ec  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__6::<>t__builder
0x8e8f1  ldloca.s 2
0x8e8f3  ldarg.0
0x8e8f4  call     T0x2B0005F9
0x8e8f9  leave    loc_8EC74
0x8e8fe  ldarg.0
0x8e8ff  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e904  stloc.2
0x8e905  ldarg.0
0x8e906  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e90b  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8e911  ldarg.0
0x8e912  ldc.i4.m1
0x8e913  dup
0x8e914  stloc.0
0x8e915  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e91a  ldloca.s 2
0x8e91c  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8e921  leave.s  loc_8E958
0x8e923  stloc.3
0x8e924  ldloc.1
0x8e925  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x8e92a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions::get_Logger()
0x8e92f  dup
0x8e930  brtrue.s loc_8E935
0x8e932  pop
0x8e933  br.s     loc_8E956
0x8e935  ldstr    aFailedToCheckF_2// "Failed to check for updates in {0}: {1}"
0x8e93a  ldc.i4.2
0x8e93b  newarr   [mscorlib]System.Object
0x8e940  dup
0x8e941  ldc.i4.0
0x8e942  ldstr    aUpdatecommandl// "UpdateCommandLineHandler"
0x8e947  stelem.ref
0x8e948  dup
0x8e949  ldc.i4.1
0x8e94a  ldloc.3
0x8e94b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8e950  stelem.ref
0x8e951  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x8e956  leave.s  loc_8E958
0x8e958  ldarg.0
0x8e959  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e95e  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::ShouldBlockRetiredChannel(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel installedProduct)
0x8e963  brfalse.s loc_8E9CA
0x8e965  ldloc.1
0x8e966  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::serviceOptions
0x8e96b  call     class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.CommandLineHandlerUtilities::ShowRetiredChannelError(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandLineHandlerServiceOptions serviceOptions)
0x8e970  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8e975  stloc.2
0x8e976  ldloca.s 2
0x8e978  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8e97d  brtrue.s loc_8E9BE
0x8e97f  ldarg.0
0x8e980  ldc.i4.4
0x8e981  dup
0x8e982  stloc.0
0x8e983  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e988  ldarg.0
0x8e989  ldloc.2
0x8e98a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e98f  ldarg.0
0x8e990  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__6::<>t__builder
0x8e995  ldloca.s 2
0x8e997  ldarg.0
0x8e998  call     T0x2B0005F9
0x8e99d  leave    loc_8EC74
0x8e9a2  ldarg.0
0x8e9a3  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e9a8  stloc.2
0x8e9a9  ldarg.0
0x8e9aa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8e9af  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x8e9b5  ldarg.0
0x8e9b6  ldc.i4.m1
0x8e9b7  dup
0x8e9b8  stloc.0
0x8e9b9  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8e9be  ldloca.s 2
0x8e9c0  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x8e9c5  leave    loc_8EC5A
0x8e9ca  ldarg.0
0x8e9cb  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e9d0  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_UpdateInformation()
0x8e9d5  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.UpdateInformationModel::get_IsUpdateAvailable()
0x8e9da  brtrue.s loc_8EA56
0x8e9dc  ldloc.1
0x8e9dd  ldarg.0
0x8e9de  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e9e3  ldarg.0
0x8e9e4  ldfld    class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel <HandleAsyncImpl>d__6::<product>5__2
0x8e9e9  call     instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::CanResume(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions options, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductSummaryModel product)
0x8e9ee  brtrue.s loc_8EA56
0x8e9f0  ldloc.1
0x8e9f1  ldarg.0
0x8e9f2  ldfld    class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions <HandleAsyncImpl>d__6::options
0x8e9f7  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.Installer.CommandLine.Handlers.UpdateCommandLineHandler::ShowNoUpdateFoundError(class Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions options)
0x8e9fc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x8ea01  stloc.2
0x8ea02  ldloca.s 2
0x8ea04  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x8ea09  brtrue.s loc_8EA4A
0x8ea0b  ldarg.0
0x8ea0c  ldc.i4.5
0x8ea0d  dup
0x8ea0e  stloc.0
0x8ea0f  stfld    int32 <HandleAsyncImpl>d__6::<>1__state
0x8ea14  ldarg.0
0x8ea15  ldloc.2
0x8ea16  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8ea1b  ldarg.0
0x8ea1c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleAsyncImpl>d__6::<>t__builder
0x8ea21  ldloca.s 2
0x8ea23  ldarg.0
0x8ea24  call     T0x2B0005F9
0x8ea29  leave    loc_8EC74
0x8ea2e  ldarg.0
0x8ea2f  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
0x8ea34  stloc.2
0x8ea35  ldarg.0
0x8ea36  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleAsyncImpl>d__6::<>u__1
  ... truncated ...
```
