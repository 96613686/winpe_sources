# Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::SetOperationTelemetryProperties

- ea: `0x3f600`
- end: `0x3f66a`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::SetOperationTelemetryProperties`
- size: `106`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7b460`
- `0x7bb60`
- `0x7bc80`
- `0x7bf40`
- `0x7c060`
- `0x7c180`
- `0x7c2a0`
- `0x7c3c0`
- `0x7c5b0`

## callees

- `0x3f770`

## string_xrefs

- `0x3f634`: `InstallSessionId: `

## pseudocode

```c

```

## disassembly

```asm
0x3f600  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x3f605  dup
0x3f606  ldsfld   string ProductOperation::OperationNameProperty
0x3f60b  ldarg.2
0x3f60c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3f611  dup
0x3f612  ldsfld   string ProductOperation::InstallSessionIdProperty
0x3f617  ldarg.1
0x3f618  ldfld    string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::InstallSessionId
0x3f61d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3f622  dup
0x3f623  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::UserRequestedOperationProperty
0x3f628  ldarg.1
0x3f629  ldfld    string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::UserRequestedOperation
0x3f62e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x3f633  ldarg.0
0x3f634  ldstr    aInstallsession_0// "InstallSessionId: "
0x3f639  ldarg.1
0x3f63a  ldfld    string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::InstallSessionId
0x3f63f  call     string [mscorlib]System.String::Concat(string, string)
0x3f644  call     T0x2B000010
0x3f649  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x3f64e  ldarg.0
0x3f64f  ldstr    aUserrequestedo_0// "UserRequestedOperation: "
0x3f654  ldarg.1
0x3f655  ldfld    string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.TelemetryContext::UserRequestedOperation
0x3f65a  call     string [mscorlib]System.String::Concat(string, string)
0x3f65f  call     T0x2B000010
0x3f664  call     instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerService::TraceMessage(string format, object[] args)
0x3f669  ret
```
