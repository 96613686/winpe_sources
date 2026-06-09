# Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ExistingRpcServerConnector::ConnectStream

- ea: `0x2f060`
- end: `0x2f0f5`
- name: `Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ExistingRpcServerConnector::ConnectStream`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2f030`

## callees

- `0x2dcb0`
- `0x2ddc0`
- `0x2dde0`
- `0x2f020`
- `0x2f060`
- `0x2f2c0`
- `0x2f2d0`
- `0x2f2e0`
- `0x34ce0`

## string_xrefs

- `0x2f090`: `Failed to connect to the installer service: `

## pseudocode

```c

```

## disassembly

```asm
0x2f060  ldarg.0
0x2f061  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ExistingRpcServerConnector::serviceOptions
0x2f066  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcStreamFactory Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_RpcStreamFactory()
0x2f06b  ldarg.1
0x2f06c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcClientStream Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcStreamFactory::CreateClientStream(string streamName)
0x2f071  stloc.0
0x2f072  call     int32 Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ExistingRpcServerConnector::GetConnectTimeout()
0x2f077  stloc.1
0x2f078  ldloc.0
0x2f079  ldloc.1
0x2f07a  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcClientStream::Connect(int32 timeoutInMs)
0x2f07f  ldarg.0
0x2f080  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcStreamConnectionValidator Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ExistingRpcServerConnector::connectionValidator
0x2f085  ldloc.0
0x2f086  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcStreamConnectionValidator::ValidateConnection(class Microsoft.VisualStudio.Setup.Installer.Rpc.IRpcStream stream)
0x2f08b  ldloc.0
0x2f08c  stloc.2
0x2f08d  leave.s  loc_2F0F3
0x2f08f  stloc.3
0x2f090  ldstr    aFailedToConnec_0// "Failed to connect to the installer serv"...
0x2f095  ldloc.3
0x2f096  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2f09b  call     string [mscorlib]System.String::Concat(string, string)
0x2f0a0  stloc.s  4
0x2f0a2  ldarg.0
0x2f0a3  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ExistingRpcServerConnector::serviceOptions
0x2f0a8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Logger()
0x2f0ad  dup
0x2f0ae  brtrue.s loc_2F0B3
0x2f0b0  pop
0x2f0b1  br.s     loc_2F0C0
0x2f0b3  ldloc.3
0x2f0b4  ldloc.s  4
0x2f0b6  call     T0x2B000010
0x2f0bb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2f0c0  ldarg.0
0x2f0c1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ExistingRpcServerConnector::serviceOptions
0x2f0c6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Telemetry()
0x2f0cb  dup
0x2f0cc  brtrue.s loc_2F0D1
0x2f0ce  pop
0x2f0cf  br.s     loc_2F0E5
0x2f0d1  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x2f0d6  ldloc.s  4
0x2f0d8  ldnull
0x2f0d9  ldloc.3
0x2f0da  ldnull
0x2f0db  ldc.i4.0
0x2f0dc  ldnull
0x2f0dd  ldc.i4.0
0x2f0de  ldnull
0x2f0df  ldc.i4.0
0x2f0e0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x2f0e5  ldloc.3
0x2f0e6  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x2f0eb  ldloc.s  4
0x2f0ed  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Pipe.PipeInitializationException::.ctor(int32 hResult, string message)
0x2f0f2  throw
0x2f0f3  ldloc.2
0x2f0f4  ret
```
