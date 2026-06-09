# Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::UpdateElevationService

- ea: `0x7ff0`
- end: `0x804e`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::UpdateElevationService`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7f40`

## callees

- `0x7480`
- `0x74c0`
- `0x7890`
- `0x78c0`
- `0x78e0`
- `0x7ff0`

## string_xrefs

- `0x8034`: `Successfully updated the registered service {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x7ff0  ldarg.1
0x7ff1  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::Stop()
0x7ff6  ldarg.1
0x7ff7  ldc.i4.1
0x7ff8  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::ServiceStopTimeout
0x7ffd  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x8002  ldarg.0
0x8003  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x8008  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceRegistrationService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ServiceRegistrationService()
0x800d  ldarg.2
0x800e  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServicePath()
0x8013  ldarg.2
0x8014  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceName()
0x8019  ldarg.2
0x801a  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceDisplayName()
0x801f  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceRegistrationService::UpdateService(string, string, string)
0x8024  ldarg.0
0x8025  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x802a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x802f  dup
0x8030  brtrue.s loc_8034
0x8032  pop
0x8033  ret
0x8034  ldstr    aSuccessfullyUp// "Successfully updated the registered ser"...
0x8039  ldc.i4.1
0x803a  newarr   [mscorlib]System.Object
0x803f  dup
0x8040  ldc.i4.0
0x8041  ldarg.2
0x8042  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceName()
0x8047  stelem.ref
0x8048  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x804d  ret
```
