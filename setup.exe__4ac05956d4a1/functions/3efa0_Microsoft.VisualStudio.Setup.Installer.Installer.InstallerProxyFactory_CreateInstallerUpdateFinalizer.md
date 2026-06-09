# Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateInstallerUpdateFinalizer

- ea: `0x3efa0`
- end: `0x3f00e`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::CreateInstallerUpdateFinalizer`
- size: `110`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3e890`
- `0x3e930`
- `0x3ea00`

## callees

- `0x2c4b0`
- `0x3e7a0`
- `0x3efa0`
- `0x40e10`

## string_xrefs

- `0x3efb1`: `Decorating installer {0} with {1}`
- `0x3efe2`: `UnelevatedInstallerUpdateFinalizer`

## pseudocode

```c

```

## disassembly

```asm
0x3efa0  ldarg.0
0x3efa1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3efa6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x3efab  dup
0x3efac  brtrue.s loc_3EFB1
0x3efae  pop
0x3efaf  br.s     loc_3EFED
0x3efb1  ldstr    aDecoratingInst// "Decorating installer {0} with {1}"
0x3efb6  ldc.i4.2
0x3efb7  newarr   [mscorlib]System.Object
0x3efbc  dup
0x3efbd  ldc.i4.0
0x3efbe  ldarg.2
0x3efbf  brtrue.s loc_3EFC4
0x3efc1  ldnull
0x3efc2  br.s     loc_3EFD6
0x3efc4  ldarg.2
0x3efc5  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3efca  dup
0x3efcb  brtrue.s loc_3EFD1
0x3efcd  pop
0x3efce  ldnull
0x3efcf  br.s     loc_3EFD6
0x3efd1  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3efd6  dup
0x3efd7  brtrue.s loc_3EFDF
0x3efd9  pop
0x3efda  ldsfld   string [mscorlib]System.String::Empty
0x3efdf  stelem.ref
0x3efe0  dup
0x3efe1  ldc.i4.1
0x3efe2  ldstr    aUnelevatedinst_0// "UnelevatedInstallerUpdateFinalizer"
0x3efe7  stelem.ref
0x3efe8  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x3efed  ldarg.0
0x3efee  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3eff3  ldarg.1
0x3eff4  ldarg.2
0x3eff5  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdateFinalizer::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions, class Microsoft.VisualStudio.Setup.Installer.Installer.IInstallerService installerService, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller installer)
0x3effa  stloc.0
0x3effb  ldarg.0
0x3effc  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.InstallerProxyFactory::serviceOptions
0x3f001  ldloc.0
0x3f002  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::FinalizeInstallerUpdateEvent
0x3f007  ldarg.3
0x3f008  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Installer.InstallerOperationTelemetryDecorator::.ctor(class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions serviceOptions, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.Installer.IInstaller installer, string eventName, class Microsoft.VisualStudio.Setup.Installer.InstallerTelemetryContext telemetryContext)
0x3f00d  ret
```
