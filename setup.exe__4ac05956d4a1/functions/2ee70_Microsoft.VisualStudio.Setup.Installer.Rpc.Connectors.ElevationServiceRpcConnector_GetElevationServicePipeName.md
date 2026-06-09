# Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::GetElevationServicePipeName

- ea: `0x2ee70`
- end: `0x2ef03`
- name: `Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::GetElevationServicePipeName`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x2ee50`

## callees

- `0x2ee70`
- `0x2f2a0`
- `0x34a30`

## string_xrefs

- `0x2ee86`: `Cannot connect to elevation service. Failed to open HKLM to read pipe name.`
- `0x2eea1`: `Cannot connect to elevation service. Failed to open `
- `0x2eed0`: `ElevationServicePipeReadError_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x2ee70  ldarg.0
0x2ee71  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x2ee76  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Registry()
0x2ee7b  ldc.i4.2
0x2ee7c  ldc.i4.0
0x2ee7d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistry::OpenBaseKey(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryHive, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.RegistryView)
0x2ee82  stloc.0
0x2ee83  ldloc.0
0x2ee84  brtrue.s loc_2EE91
0x2ee86  ldstr    aCannotConnectT// "Cannot connect to elevation service. Fa"...
0x2ee8b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2ee90  throw
0x2ee91  ldloc.0
0x2ee92  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceRegistryKey
0x2ee97  ldc.i4.0
0x2ee98  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IRegistryKey::OpenSubKey(string, bool)
0x2ee9d  stloc.1
0x2ee9e  ldloc.1
0x2ee9f  brtrue.s loc_2EEB6
0x2eea1  ldstr    aCannotConnectT_0// "Cannot connect to elevation service. Fa"...
0x2eea6  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceRegistryKey
0x2eeab  call     string [mscorlib]System.String::Concat(string, string)
0x2eeb0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2eeb5  throw
0x2eeb6  ldloc.1
0x2eeb7  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServicePipeNameRegistryValue
0x2eebc  ldnull
0x2eebd  call     T0x2B000227
0x2eec2  stloc.2
0x2eec3  ldloc.2
0x2eec4  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string)
0x2eec9  brfalse.s loc_2EEE9
0x2eecb  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x2eed0  ldstr    aElevationservi_7// "ElevationServicePipeReadError_Args1"
0x2eed5  ldc.i4.1
0x2eed6  newarr   [mscorlib]System.Object
0x2eedb  dup
0x2eedc  ldc.i4.0
0x2eedd  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDisplayName
0x2eee2  stelem.ref
0x2eee3  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Pipe.LocalizedPipeException::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId, object[] args)
0x2eee8  throw
0x2eee9  ldloc.2
0x2eeea  stloc.3
0x2eeeb  leave.s  loc_2EF01
0x2eeed  ldloc.1
0x2eeee  brfalse.s loc_2EEF6
0x2eef0  ldloc.1
0x2eef1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2eef6  endfinally
0x2eef7  ldloc.0
0x2eef8  brfalse.s loc_2EF00
0x2eefa  ldloc.0
0x2eefb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ef00  endfinally
0x2ef01  ldloc.3
0x2ef02  ret
```
