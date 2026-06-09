# Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::StartElevationService

- ea: `0x2ed60`
- end: `0x2ee46`
- name: `Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::StartElevationService`
- size: `230`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2ece0`
- `0x74e10`

## callees

- `0x2ed60`
- `0x2f2d0`
- `0x2f3a0`
- `0x34a30`

## string_xrefs

- `0x2ed83`: `ElevationServiceNotRegisteredError_Args2`
- `0x2edb6`: `Cannot start elevation service.`
- `0x2eded`: `Failed to start the elevation service in {0} seconds.`
- `0x2ee17`: `ElevationServiceTimeoutError_Args2`

## pseudocode

```c

```

## disassembly

```asm
0x2ed60  ldarg.0
0x2ed61  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x2ed66  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceControllerFactory Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_ServiceControllerFactory()
0x2ed6b  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceName
0x2ed70  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceControllerFactory::Create(string)
0x2ed75  stloc.0
0x2ed76  ldloc.0
0x2ed77  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::get_Exists()
0x2ed7c  brtrue.s loc_2EDC7
0x2ed7e  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x2ed83  ldstr    aElevationservi_5// "ElevationServiceNotRegisteredError_Args"...
0x2ed88  ldc.i4.2
0x2ed89  newarr   [mscorlib]System.Object
0x2ed8e  dup
0x2ed8f  ldc.i4.0
0x2ed90  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDisplayName
0x2ed95  stelem.ref
0x2ed96  dup
0x2ed97  ldc.i4.1
0x2ed98  ldsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerConstants::LatestVersionDownloadLink
0x2ed9d  stelem.ref
0x2ed9e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Pipe.LocalizedPipeException::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId, object[] args)
0x2eda3  stloc.1
0x2eda4  ldarg.0
0x2eda5  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x2edaa  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Logger()
0x2edaf  dup
0x2edb0  brtrue.s loc_2EDB5
0x2edb2  pop
0x2edb3  br.s     loc_2EDC5
0x2edb5  ldloc.1
0x2edb6  ldstr    aCannotStartEle// "Cannot start elevation service."
0x2edbb  call     T0x2B000010
0x2edc0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2edc5  ldloc.1
0x2edc6  throw
0x2edc7  ldloc.0
0x2edc8  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::Start()
0x2edcd  ldloc.0
0x2edce  ldc.i4.4
0x2edcf  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::ServiceStartTimeout
0x2edd4  callvirt instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.IServiceController::WaitForStatus(valuetype [System.ServiceProcess]System.ServiceProcess.ServiceControllerStatus, valuetype [mscorlib]System.TimeSpan)
0x2edd9  leave.s  loc_2EE45
0x2eddb  pop
0x2eddc  ldarg.0
0x2eddd  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::serviceOptions
0x2ede2  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Logger()
0x2ede7  dup
0x2ede8  brtrue.s loc_2EDED
0x2edea  pop
0x2edeb  br.s     loc_2EE12
0x2eded  ldstr    aFailedToStartT_0// "Failed to start the elevation service i"...
0x2edf2  ldc.i4.1
0x2edf3  newarr   [mscorlib]System.Object
0x2edf8  dup
0x2edf9  ldc.i4.0
0x2edfa  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::ServiceStartTimeout
0x2edff  stloc.2
0x2ee00  ldloca.s 2
0x2ee02  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x2ee07  box      [mscorlib]System.Double
0x2ee0c  stelem.ref
0x2ee0d  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2ee12  call     class [mscorlib]System.Resources.ResourceManager [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ResourceManager()
0x2ee17  ldstr    aElevationservi_6// "ElevationServiceTimeoutError_Args2"
0x2ee1c  ldc.i4.2
0x2ee1d  newarr   [mscorlib]System.Object
0x2ee22  dup
0x2ee23  ldc.i4.0
0x2ee24  ldsfld   string [VSInstallerElevationService.Contracts]Microsoft.VisualStudio.Setup.ElevationServiceConstants::ElevationServiceDisplayName
0x2ee29  stelem.ref
0x2ee2a  dup
0x2ee2b  ldc.i4.1
0x2ee2c  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevationServiceRpcConnector::ServiceStartTimeout
0x2ee31  stloc.2
0x2ee32  ldloca.s 2
0x2ee34  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x2ee39  box      [mscorlib]System.Double
0x2ee3e  stelem.ref
0x2ee3f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Pipe.LocalizedPipeException::.ctor(class [mscorlib]System.Resources.ResourceManager resources, string resourceId, object[] args)
0x2ee44  throw
0x2ee45  ret
```
