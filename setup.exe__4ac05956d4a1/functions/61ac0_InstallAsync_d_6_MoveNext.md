# <InstallAsync>d__6::MoveNext

- ea: `0x61ac0`
- end: `0x61e4b`
- name: `<InstallAsync>d__6::MoveNext`
- size: `907`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x7140`
- `0x76d0`
- `0x76e0`
- `0x61320`
- `0x61ac0`

## string_xrefs

- `0x61c49`: `Failed to download VSUpdater.`
- `0x61b48`: `Starting VSUpdater installation.`
- `0x61b79`: `Failed to determine if the VSUpdater is installed`
- `0x61c18`: `VSUpdater is already installed.`
- `0x61cd5`: `Extracting VSUpdater from: {0}`
- `0x61d15`: `Failed to extract VSUpdater.`
- `0x61d92`: `VSUpdater installed successfully to: {0}`
- `0x61dc8`: `Failed to register VSUpdater.`
- `0x61dde`: `Successfully installed VSUpdater.`

## pseudocode

```c

```

## disassembly

```asm
0x61ac0  ldarg.0
0x61ac1  ldfld    int32 <InstallAsync>d__6::<>1__state
0x61ac6  stloc.0
0x61ac7  ldarg.0
0x61ac8  ldfld    class Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper <InstallAsync>d__6::<>4__this
0x61acd  stloc.1
0x61ace  ldloc.0
0x61acf  ldc.i4.2
0x61ad0  ble.un.s loc_61B24
0x61ad2  ldarg.0
0x61ad3  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x61ad8  stfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61add  ldarg.0
0x61ade  ldfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61ae3  ldarg.0
0x61ae4  ldfld    class Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper <InstallAsync>d__6::<>4__this
0x61ae9  stfld    class Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper <>c__DisplayClass6_0::<>4__this
0x61aee  ldarg.0
0x61aef  ldfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61af4  ldarg.0
0x61af5  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <InstallAsync>d__6::cancellationToken
0x61afa  stfld    valuetype [mscorlib]System.Threading.CancellationToken <>c__DisplayClass6_0::cancellationToken
0x61aff  ldarg.0
0x61b00  ldloc.1
0x61b01  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61b06  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Telemetry()
0x61b0b  dup
0x61b0c  brtrue.s loc_61B12
0x61b0e  pop
0x61b0f  ldnull
0x61b10  br.s     loc_61B1F
0x61b12  ldsfld   string Events::InstallEvent
0x61b17  ldnull
0x61b18  ldc.i4.0
0x61b19  ldc.i4.0
0x61b1a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x61b1f  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61b24  nop
0x61b25  ldloc.0
0x61b26  switch   loc_61BBF, loc_61C91, loc_61D5D
0x61b37  ldloc.1
0x61b38  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61b3d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61b42  dup
0x61b43  brtrue.s loc_61B48
0x61b45  pop
0x61b46  br.s     loc_61B57
0x61b48  ldstr    aStartingVsupda_0// "Starting VSUpdater installation."
0x61b4d  call     T0x2B000010
0x61b52  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x61b57  ldloc.1
0x61b58  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61b5d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61b62  ldarg.0
0x61b63  ldfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61b68  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<bool> <>c__DisplayClass6_0::<InstallAsync>b__1()
0x61b6e  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor(object, native int)
0x61b73  ldarg.0
0x61b74  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61b79  ldstr    aFailedToDeterm_0// "Failed to determine if the VSUpdater is"...
0x61b7e  call     T0x2B000400
0x61b83  ldc.i4.0
0x61b84  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool>::ConfigureAwait(!!T0)
0x61b89  stloc.s  4
0x61b8b  ldloca.s 4
0x61b8d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<bool>::GetAwaiter()
0x61b92  stloc.3
0x61b93  ldloca.s 3
0x61b95  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::get_IsCompleted()
0x61b9a  brtrue.s loc_61BDB
0x61b9c  ldarg.0
0x61b9d  ldc.i4.0
0x61b9e  dup
0x61b9f  stloc.0
0x61ba0  stfld    int32 <InstallAsync>d__6::<>1__state
0x61ba5  ldarg.0
0x61ba6  ldloc.3
0x61ba7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <InstallAsync>d__6::<>u__1
0x61bac  ldarg.0
0x61bad  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InstallAsync>d__6::<>t__builder
0x61bb2  ldloca.s 3
0x61bb4  ldarg.0
0x61bb5  call     T0x2B000401
0x61bba  leave    loc_61E4A
0x61bbf  ldarg.0
0x61bc0  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <InstallAsync>d__6::<>u__1
0x61bc5  stloc.3
0x61bc6  ldarg.0
0x61bc7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool> <InstallAsync>d__6::<>u__1
0x61bcc  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>
0x61bd2  ldarg.0
0x61bd3  ldc.i4.m1
0x61bd4  dup
0x61bd5  stloc.0
0x61bd6  stfld    int32 <InstallAsync>d__6::<>1__state
0x61bdb  ldloca.s 3
0x61bdd  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<bool>::GetResult()
0x61be2  stloc.2
0x61be3  ldarg.0
0x61be4  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61be9  dup
0x61bea  brtrue.s loc_61BEF
0x61bec  pop
0x61bed  br.s     loc_61C04
0x61bef  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::get_Properties()
0x61bf4  ldsfld   string Properties::IsInstalled
0x61bf9  ldloc.2
0x61bfa  box      [mscorlib]System.Boolean
0x61bff  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x61c04  ldloc.2
0x61c05  brfalse.s loc_61C27
0x61c07  ldloc.1
0x61c08  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61c0d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61c12  ldarg.0
0x61c13  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61c18  ldstr    aVsupdaterIsAlr// "VSUpdater is already installed."
0x61c1d  call     void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LoggingUtilities::LogAndRecordSuccess(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation, string)
0x61c22  leave    loc_61E29
0x61c27  ldloc.1
0x61c28  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61c2d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61c32  ldarg.0
0x61c33  ldfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61c38  ldftn    instance class [mscorlib]System.Threading.Tasks.Task`1<string> <>c__DisplayClass6_0::<InstallAsync>b__2()
0x61c3e  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task`1<string>>::.ctor(object, native int)
0x61c43  ldarg.0
0x61c44  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61c49  ldstr    aFailedToDownlo_1// "Failed to download VSUpdater."
0x61c4e  call     T0x2B000402
0x61c53  ldc.i4.0
0x61c54  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::ConfigureAwait(!!T0)
0x61c59  stloc.s  7
0x61c5b  ldloca.s 7
0x61c5d  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1<string>::GetAwaiter()
0x61c62  stloc.s  6
0x61c64  ldloca.s 6
0x61c66  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string>::get_IsCompleted()
0x61c6b  brtrue.s loc_61CAE
0x61c6d  ldarg.0
0x61c6e  ldc.i4.1
0x61c6f  dup
0x61c70  stloc.0
0x61c71  stfld    int32 <InstallAsync>d__6::<>1__state
0x61c76  ldarg.0
0x61c77  ldloc.s  6
0x61c79  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string> <InstallAsync>d__6::<>u__2
0x61c7e  ldarg.0
0x61c7f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InstallAsync>d__6::<>t__builder
0x61c84  ldloca.s 6
0x61c86  ldarg.0
0x61c87  call     T0x2B000403
0x61c8c  leave    loc_61E4A
0x61c91  ldarg.0
0x61c92  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string> <InstallAsync>d__6::<>u__2
0x61c97  stloc.s  6
0x61c99  ldarg.0
0x61c9a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string> <InstallAsync>d__6::<>u__2
0x61c9f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string>
0x61ca5  ldarg.0
0x61ca6  ldc.i4.m1
0x61ca7  dup
0x61ca8  stloc.0
0x61ca9  stfld    int32 <InstallAsync>d__6::<>1__state
0x61cae  ldloca.s 6
0x61cb0  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable`1/ConfiguredTaskAwaiter<string>::GetResult()
0x61cb5  stloc.s  5
0x61cb7  ldarg.0
0x61cb8  ldfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61cbd  ldloc.s  5
0x61cbf  stfld    string <>c__DisplayClass6_0::downloadPath
0x61cc4  ldloc.1
0x61cc5  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61cca  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61ccf  dup
0x61cd0  brtrue.s loc_61CD5
0x61cd2  pop
0x61cd3  br.s     loc_61CF3
0x61cd5  ldstr    aExtractingVsup// "Extracting VSUpdater from: {0}"
0x61cda  ldc.i4.1
0x61cdb  newarr   [mscorlib]System.Object
0x61ce0  dup
0x61ce1  ldc.i4.0
0x61ce2  ldarg.0
0x61ce3  ldfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61ce8  ldfld    string <>c__DisplayClass6_0::downloadPath
0x61ced  stelem.ref
0x61cee  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x61cf3  ldloc.1
0x61cf4  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61cf9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61cfe  ldarg.0
0x61cff  ldfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61d04  ldftn    instance class [mscorlib]System.Threading.Tasks.Task <>c__DisplayClass6_0::<InstallAsync>b__0()
0x61d0a  newobj   instance void class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task>::.ctor(object, native int)
0x61d0f  ldarg.0
0x61d10  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61d15  ldstr    aFailedToExtrac// "Failed to extract VSUpdater."
0x61d1a  call     class [mscorlib]System.Threading.Tasks.Task [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LoggingUtilities::RunActionWithFailureDiagnosticsAsync(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [mscorlib]System.Func`1<class [mscorlib]System.Threading.Tasks.Task>, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation, string)
0x61d1f  ldc.i4.0
0x61d20  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x61d25  stloc.s  9
0x61d27  ldloca.s 9
0x61d29  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x61d2e  stloc.s  8
0x61d30  ldloca.s 8
0x61d32  call     instance bool [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::get_IsCompleted()
0x61d37  brtrue.s loc_61D7A
0x61d39  ldarg.0
0x61d3a  ldc.i4.2
0x61d3b  dup
0x61d3c  stloc.0
0x61d3d  stfld    int32 <InstallAsync>d__6::<>1__state
0x61d42  ldarg.0
0x61d43  ldloc.s  8
0x61d45  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InstallAsync>d__6::<>u__3
0x61d4a  ldarg.0
0x61d4b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InstallAsync>d__6::<>t__builder
0x61d50  ldloca.s 8
0x61d52  ldarg.0
0x61d53  call     T0x2B000404
0x61d58  leave    loc_61E4A
0x61d5d  ldarg.0
0x61d5e  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InstallAsync>d__6::<>u__3
0x61d63  stloc.s  8
0x61d65  ldarg.0
0x61d66  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter <InstallAsync>d__6::<>u__3
0x61d6b  initobj  [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter
0x61d71  ldarg.0
0x61d72  ldc.i4.m1
0x61d73  dup
0x61d74  stloc.0
0x61d75  stfld    int32 <InstallAsync>d__6::<>1__state
0x61d7a  ldloca.s 8
0x61d7c  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x61d81  ldloc.1
0x61d82  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61d87  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61d8c  dup
0x61d8d  brtrue.s loc_61D92
0x61d8f  pop
0x61d90  br.s     loc_61DAB
0x61d92  ldstr    aVsupdaterInsta// "VSUpdater installed successfully to: {0"...
0x61d97  ldc.i4.1
0x61d98  newarr   [mscorlib]System.Object
0x61d9d  dup
0x61d9e  ldc.i4.0
0x61d9f  ldloc.1
0x61da0  call     instance string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetInstallationDirectory()
0x61da5  stelem.ref
0x61da6  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x61dab  ldloc.1
0x61dac  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x61db1  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x61db6  ldloc.1
0x61db7  ldftn    instance void Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::RegisterVSUpdater()
0x61dbd  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x61dc2  ldarg.0
0x61dc3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61dc8  ldstr    aFailedToRegist// "Failed to register VSUpdater."
0x61dcd  call     void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LoggingUtilities::RunActionWithFailureDiagnostics(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [mscorlib]System.Action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation, string)
0x61dd2  ldarg.0
0x61dd3  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61dd8  dup
0x61dd9  brtrue.s loc_61DDE
0x61ddb  pop
0x61ddc  br.s     loc_61DE8
0x61dde  ldstr    aSuccessfullyIn// "Successfully installed VSUpdater."
0x61de3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x61de8  leave.s  loc_61E29
0x61dea  ldloc.0
0x61deb  ldc.i4.0
0x61dec  bge.s    loc_61E01
0x61dee  ldarg.0
0x61def  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61df4  brfalse.s loc_61E01
0x61df6  ldarg.0
0x61df7  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61dfc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61e01  endfinally
0x61e02  stloc.s  0xA
0x61e04  ldarg.0
0x61e05  ldc.i4.s 0xFE
0x61e07  stfld    int32 <InstallAsync>d__6::<>1__state
0x61e0c  ldarg.0
0x61e0d  ldnull
0x61e0e  stfld    class <>c__DisplayClass6_0 <InstallAsync>d__6::<>8__1
0x61e13  ldarg.0
0x61e14  ldnull
0x61e15  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation <InstallAsync>d__6::<operation>5__2
0x61e1a  ldarg.0
0x61e1b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <InstallAsync>d__6::<>t__builder
0x61e20  ldloc.s  0xA
0x61e22  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x61e27  leave.s  loc_61E4A
0x61e29  ldarg.0
0x61e2a  ldc.i4.s 0xFE
0x61e2c  stfld    int32 <InstallAsync>d__6::<>1__state
0x61e31  ldarg.0
0x61e32  ldnull
  ... truncated ...
```
