# Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::UninstallAsync

- ea: `0x6fa0`
- end: `0x7067`
- name: `Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::UninstallAsync`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x6fa0`
- `0x7140`
- `0x76d0`
- `0x76e0`
- `0x61400`

## string_xrefs

- `0x6fde`: `Starting VSUpdater uninstallation.`
- `0x7011`: `Failed to unregister VSUpdater.`
- `0x7033`: `Failed to delete VSUpdater directory`
- `0x7049`: `Successfully uninstalled VSUpdater`

## pseudocode

```c

```

## disassembly

```asm
0x6fa0  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x6fa5  stloc.0
0x6fa6  ldloc.0
0x6fa7  ldarg.0
0x6fa8  stfld    class Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper <>c__DisplayClass7_0::<>4__this
0x6fad  ldarg.0
0x6fae  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6fb3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Telemetry()
0x6fb8  dup
0x6fb9  brtrue.s loc_6FBF
0x6fbb  pop
0x6fbc  ldnull
0x6fbd  br.s     loc_6FCC
0x6fbf  ldsfld   string Events::UninstallEvent
0x6fc4  ldnull
0x6fc5  ldc.i4.0
0x6fc6  ldc.i4.0
0x6fc7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::StartOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, bool, bool)
0x6fcc  stloc.1
0x6fcd  ldarg.0
0x6fce  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6fd3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x6fd8  dup
0x6fd9  brtrue.s loc_6FDE
0x6fdb  pop
0x6fdc  br.s     loc_6FED
0x6fde  ldstr    aStartingVsupda// "Starting VSUpdater uninstallation."
0x6fe3  call     T0x2B000010
0x6fe8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x6fed  ldloc.0
0x6fee  ldarg.0
0x6fef  call     instance string Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::GetInstallationDirectory()
0x6ff4  stfld    string <>c__DisplayClass7_0::installDirectory
0x6ff9  ldarg.0
0x6ffa  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x6fff  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x7004  ldarg.0
0x7005  ldftn    instance void Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::UnregisterVSUpdater()
0x700b  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7010  ldloc.1
0x7011  ldstr    aFailedToUnregi// "Failed to unregister VSUpdater."
0x7016  call     void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LoggingUtilities::RunActionWithFailureDiagnostics(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [mscorlib]System.Action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation, string)
0x701b  ldarg.0
0x701c  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x7021  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x7026  ldloc.0
0x7027  ldftn    instance void <>c__DisplayClass7_0::<UninstallAsync>b__0()
0x702d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x7032  ldloc.1
0x7033  ldstr    aFailedToDelete// "Failed to delete VSUpdater directory"
0x7038  call     void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LoggingUtilities::RunActionWithFailureDiagnostics(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [mscorlib]System.Action, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation, string)
0x703d  ldarg.0
0x703e  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions Microsoft.VisualStudio.Setup.Services.VSUpdaterBootstrapper::serviceOptions
0x7043  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.VSUpdaterBootstrapperServiceOptions::get_Logger()
0x7048  ldloc.1
0x7049  ldstr    aSuccessfullyUn// "Successfully uninstalled VSUpdater"
0x704e  call     void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LoggingUtilities::LogAndRecordSuccess(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation, string)
0x7053  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::get_CompletedTask()
0x7058  stloc.2
0x7059  leave.s  loc_7065
0x705b  ldloc.1
0x705c  brfalse.s loc_7064
0x705e  ldloc.1
0x705f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7064  endfinally
0x7065  ldloc.2
0x7066  ret
```
