# Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::InstallElevationService

- ea: `0x7f40`
- end: `0x7fe6`
- name: `Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::InstallElevationService`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x62200`

## callees

- `0x7480`
- `0x74c0`
- `0x74f0`
- `0x7890`
- `0x78c0`
- `0x78e0`
- `0x7900`
- `0x7f40`
- `0x7ff0`

## string_xrefs

- `0x7f70`: `{0} is already registered. Updating the register.`
- `0x7fcc`: `Successfully registered service {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x7f40  ldarg.0
0x7f41  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x7f46  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceControllerFactory Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ServiceControllerFactory()
0x7f4b  ldarg.1
0x7f4c  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceName()
0x7f51  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceControllerFactory::Create(string)
0x7f56  stloc.0
0x7f57  ldloc.0
0x7f58  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::get_Exists()
0x7f5d  brfalse.s loc_7F92
0x7f5f  ldarg.0
0x7f60  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x7f65  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x7f6a  dup
0x7f6b  brtrue.s loc_7F70
0x7f6d  pop
0x7f6e  br.s     loc_7F89
0x7f70  ldstr    a0IsAlreadyRegi// "{0} is already registered. Updating the"...
0x7f75  ldc.i4.1
0x7f76  newarr   [mscorlib]System.Object
0x7f7b  dup
0x7f7c  ldc.i4.0
0x7f7d  ldarg.1
0x7f7e  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceName()
0x7f83  stelem.ref
0x7f84  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7f89  ldarg.0
0x7f8a  ldloc.0
0x7f8b  ldarg.1
0x7f8c  call     instance void Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::UpdateElevationService(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController service, class Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions options)
0x7f91  ret
0x7f92  ldarg.0
0x7f93  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x7f98  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceRegistrationService Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_ServiceRegistrationService()
0x7f9d  ldarg.1
0x7f9e  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServicePath()
0x7fa3  ldarg.1
0x7fa4  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceName()
0x7fa9  ldarg.1
0x7faa  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceDisplayName()
0x7faf  ldarg.1
0x7fb0  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceDescription()
0x7fb5  ldc.i4.0
0x7fb6  ldc.i4.1
0x7fb7  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceRegistrationService::InstallService(string, string, string, string, bool, bool)
0x7fbc  ldarg.0
0x7fbd  ldfld    class Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions Microsoft.VisualStudio.Setup.Bootstrapper.InstallerFinalizerService::serviceOptions
0x7fc2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.ServiceOptions.InstallerFinalizerServiceOptions::get_Logger()
0x7fc7  dup
0x7fc8  brtrue.s loc_7FCC
0x7fca  pop
0x7fcb  ret
0x7fcc  ldstr    aSuccessfullyRe// "Successfully registered service {0}."
0x7fd1  ldc.i4.1
0x7fd2  newarr   [mscorlib]System.Object
0x7fd7  dup
0x7fd8  ldc.i4.0
0x7fd9  ldarg.1
0x7fda  callvirt instance string Microsoft.VisualStudio.Setup.Bootstrapper.FinalizeInstallerOptions::get_ElevationServiceName()
0x7fdf  stelem.ref
0x7fe0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x7fe5  ret
```
