# Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::UninstallElevationService

- ea: `0x8050`
- end: `0x80d7`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::UninstallElevationService`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x62300`

## callees

- `0x7480`
- `0x74c0`
- `0x74f0`
- `0x8050`

## string_xrefs

- `0x80c2`: `Successfully unregistered service {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x8050  ldarg.0
0x8051  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x8056  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceControllerFactory Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ServiceControllerFactory()
0x805b  ldarg.1
0x805c  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceControllerFactory::Create(string)
0x8061  stloc.0
0x8062  ldloc.0
0x8063  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::get_Exists()
0x8068  brtrue.s loc_808F
0x806a  ldarg.0
0x806b  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x8070  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x8075  dup
0x8076  brtrue.s loc_807A
0x8078  pop
0x8079  ret
0x807a  ldstr    a0IsNotRegister// "{0} is not registered, so skipping remo"...
0x807f  ldc.i4.1
0x8080  newarr   [mscorlib]System.Object
0x8085  dup
0x8086  ldc.i4.0
0x8087  ldarg.1
0x8088  stelem.ref
0x8089  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x808e  ret
0x808f  ldloc.0
0x8090  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::Stop()
0x8095  ldloc.0
0x8096  ldc.i4.1
0x8097  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::ServiceStopTimeout
0x809c  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x80a1  ldarg.0
0x80a2  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x80a7  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceRegistrationService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ServiceRegistrationService()
0x80ac  ldarg.1
0x80ad  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceRegistrationService::UninstallService(string)
0x80b2  ldarg.0
0x80b3  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x80b8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x80bd  dup
0x80be  brtrue.s loc_80C2
0x80c0  pop
0x80c1  ret
0x80c2  ldstr    aSuccessfullyUn_0// "Successfully unregistered service {0}."
0x80c7  ldc.i4.1
0x80c8  newarr   [mscorlib]System.Object
0x80cd  dup
0x80ce  ldc.i4.0
0x80cf  ldarg.1
0x80d0  stelem.ref
0x80d1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x80d6  ret
```
