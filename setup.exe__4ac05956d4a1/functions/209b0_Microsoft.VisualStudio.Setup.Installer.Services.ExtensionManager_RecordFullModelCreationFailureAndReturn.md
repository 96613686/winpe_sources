# Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::RecordFullModelCreationFailureAndReturn

- ea: `0x209b0`
- end: `0x20a03`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::RecordFullModelCreationFailureAndReturn`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x20540`
- `0x20d30`
- `0x6e680`

## callees

- `0x9cc0`
- `0x209b0`
- `0x2bcb0`

## string_xrefs

- `0x209b0`: `Failed to create a full extension model.`

## pseudocode

```c

```

## disassembly

```asm
0x209b0  ldstr    aFailedToCreate_1// "Failed to create a full extension model"...
0x209b5  stloc.0
0x209b6  ldarg.s  4
0x209b8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x209bd  brtrue.s loc_209CD
0x209bf  ldloc.0
0x209c0  ldstr    asc_9D4A4// " "
0x209c5  ldarg.s  4
0x209c7  call     string [mscorlib]System.String::Concat(string, string, string)
0x209cc  stloc.0
0x209cd  ldarg.1
0x209ce  brfalse.s loc_209D7
0x209d0  ldarg.1
0x209d1  ldloc.0
0x209d2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordFailure(string)
0x209d7  ldarg.0
0x209d8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x209dd  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x209e2  dup
0x209e3  brtrue.s loc_209E8
0x209e5  pop
0x209e6  br.s     loc_209F3
0x209e8  ldloc.0
0x209e9  call     T0x2B000010
0x209ee  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x209f3  ldnull
0x209f4  ldarg.2
0x209f5  callvirt instance string [System]System.Uri::get_OriginalString()
0x209fa  ldarg.3
0x209fb  ldc.i4.0
0x209fc  ldc.i4.6
0x209fd  newobj   instance void Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::.ctor(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel Model, string ExtensionNameOrUri, valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState ErrorState, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExtensionOrigin Origin, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Security.VerificationResult VerificationResult)
0x20a02  ret
```
