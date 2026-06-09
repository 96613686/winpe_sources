# Microsoft.VisualStudio.Setup.Installer.Rpc.RpcClient::CreateRpcClient

- ea: `0x2dea0`
- end: `0x2df1a`
- name: `Microsoft.VisualStudio.Setup.Installer.Rpc.RpcClient::CreateRpcClient`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x74330`

## callees

- `0x2dea0`
- `0x2df20`
- `0x2e620`
- `0x2e630`
- `0x2e6f0`

## string_xrefs

- `0x2dec4`: `Failed to connect to the installer service: `

## pseudocode

```c

```

## disassembly

```asm
0x2dea0  ldsfld   class Microsoft.VisualStudio.Setup.Installer.Rpc.StreamJsonRpcFactory Microsoft.VisualStudio.Setup.Installer.Rpc.StreamJsonRpcFactory::Default
0x2dea5  ldarg.1
0x2dea6  ldnull
0x2dea7  call     T0x2B000010
0x2deac  callvirt instance class [StreamJsonRpc]StreamJsonRpc.JsonRpc Microsoft.VisualStudio.Setup.Installer.Rpc.StreamJsonRpcFactory::Create(class [mscorlib]System.IO.Stream stream, [opt] class [StreamJsonRpc]StreamJsonRpc.JsonRpcTargetOptions options, object[] targets)
0x2deb1  stloc.0
0x2deb2  ldarg.0
0x2deb3  ldloc.0
0x2deb4  call     instance void Microsoft.VisualStudio.Setup.Installer.Rpc.RpcClient::RegisterClientServices(class [StreamJsonRpc]StreamJsonRpc.JsonRpc rpc)
0x2deb9  ldloc.0
0x2deba  callvirt instance void [StreamJsonRpc]StreamJsonRpc.JsonRpc::StartListening()
0x2debf  ldloc.0
0x2dec0  stloc.1
0x2dec1  leave.s  loc_2DF18
0x2dec3  stloc.2
0x2dec4  ldstr    aFailedToConnec_0// "Failed to connect to the installer serv"...
0x2dec9  ldloc.2
0x2deca  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2decf  call     string [mscorlib]System.String::Concat(string, string)
0x2ded4  stloc.3
0x2ded5  ldarg.0
0x2ded6  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.RpcServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.RpcClient::serviceOptions
0x2dedb  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Rpc.RpcServiceOptions::get_Logger()
0x2dee0  dup
0x2dee1  brtrue.s loc_2DEE6
0x2dee3  pop
0x2dee4  br.s     loc_2DEF2
0x2dee6  ldloc.2
0x2dee7  ldloc.3
0x2dee8  call     T0x2B000010
0x2deed  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2def2  ldarg.0
0x2def3  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.RpcServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.RpcClient::serviceOptions
0x2def8  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.Rpc.RpcServiceOptions::get_Telemetry()
0x2defd  dup
0x2defe  brtrue.s loc_2DF03
0x2df00  pop
0x2df01  br.s     loc_2DF16
0x2df03  ldsfld   string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.TelemetryConstants::FAULTEVENT
0x2df08  ldloc.3
0x2df09  ldnull
0x2df0a  ldloc.2
0x2df0b  ldnull
0x2df0c  ldc.i4.0
0x2df0d  ldnull
0x2df0e  ldc.i4.0
0x2df0f  ldnull
0x2df10  ldc.i4.0
0x2df11  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x2df16  rethrow
0x2df18  ldloc.1
0x2df19  ret
```
