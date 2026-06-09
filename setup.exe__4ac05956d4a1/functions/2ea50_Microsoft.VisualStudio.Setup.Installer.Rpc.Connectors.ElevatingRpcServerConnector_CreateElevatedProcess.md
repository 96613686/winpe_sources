# Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::CreateElevatedProcess

- ea: `0x2ea50`
- end: `0x2ec8c`
- name: `Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::CreateElevatedProcess`
- size: `572`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2e9c0`
- `0x2ea00`

## callees

- `0x219d0`
- `0x219e0`
- `0x21a20`
- `0x22c90`
- `0x29bf0`
- `0x2ea50`
- `0x2f2c0`
- `0x2f2d0`
- `0x2f300`
- `0x2f350`
- `0x2f360`
- `0x2f370`
- `0x34cd0`
- `0x34ce0`
- `0x58d70`

## string_xrefs

- `0x2eb48`: `Failed to get window handle during elevation: `

## pseudocode

```c

```

## disassembly

```asm
0x2ea50  ldarg.0
0x2ea51  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2ea56  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_ProcessService()
0x2ea5b  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::GetCurrentProcess()
0x2ea60  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::get_Id()
0x2ea65  stloc.0
0x2ea66  ldarg.0
0x2ea67  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2ea6c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_ProcessService()
0x2ea71  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService::CreateProcess()
0x2ea76  stloc.1
0x2ea77  ldloc.1
0x2ea78  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x2ea7d  ldarg.0
0x2ea7e  ldfld    string Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serverPath
0x2ea83  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_FileName(string)
0x2ea88  ldloc.1
0x2ea89  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x2ea8e  ldstr    aRunas// "runas"
0x2ea93  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Verb(string)
0x2ea98  ldarg.0
0x2ea99  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2ea9e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Telemetry()
0x2eaa3  dup
0x2eaa4  brtrue.s loc_2EAAA
0x2eaa6  pop
0x2eaa7  ldnull
0x2eaa8  br.s     loc_2EAAF
0x2eaaa  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::SerializeSettings()
0x2eaaf  stloc.2
0x2eab0  ldarg.0
0x2eab1  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2eab6  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.Globalization.ILocaleService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_LocaleService()
0x2eabb  dup
0x2eabc  brtrue.s loc_2EAC2
0x2eabe  pop
0x2eabf  ldnull
0x2eac0  br.s     loc_2EAD3
0x2eac2  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.Installer.Services.Globalization.ILocaleService::GetLocale()
0x2eac7  dup
0x2eac8  brtrue.s loc_2EACE
0x2eaca  pop
0x2eacb  ldnull
0x2eacc  br.s     loc_2EAD3
0x2eace  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x2ead3  dup
0x2ead4  brtrue.s loc_2EAE6
0x2ead6  pop
0x2ead7  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2eadc  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0x2eae1  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x2eae6  stloc.3
0x2eae7  ldarg.0
0x2eae8  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2eaed  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_InstallerSettings()
0x2eaf2  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_CampaignId()
0x2eaf7  stloc.s  4
0x2eaf9  ldarg.0
0x2eafa  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2eaff  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_InstallerSettings()
0x2eb04  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Passive()
0x2eb09  stloc.s  5
0x2eb0b  ldarg.0
0x2eb0c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2eb11  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_InstallerSettings()
0x2eb16  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Quiet()
0x2eb1b  stloc.s  6
0x2eb1d  ldc.i4.0
0x2eb1e  conv.i8
0x2eb1f  stloc.s  7
0x2eb21  ldarg.0
0x2eb22  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2eb27  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.IWindowService Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_WindowService()
0x2eb2c  dup
0x2eb2d  brtrue.s loc_2EB34
0x2eb2f  pop
0x2eb30  ldc.i4.0
0x2eb31  conv.i8
0x2eb32  br.s     loc_2EB42
0x2eb34  callvirt instance native int Microsoft.VisualStudio.Setup.Installer.Services.IWindowService::GetWindowHandle()
0x2eb39  stloc.s  9
0x2eb3b  ldloca.s 9
0x2eb3d  call     instance int64 [mscorlib]System.IntPtr::ToInt64()
0x2eb42  stloc.s  7
0x2eb44  leave.s  loc_2EBA2
0x2eb46  stloc.s  0xA
0x2eb48  ldstr    aFailedToGetWin// "Failed to get window handle during elev"...
0x2eb4d  ldloc.s  0xA
0x2eb4f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2eb54  call     string [mscorlib]System.String::Concat(string, string)
0x2eb59  stloc.s  0xB
0x2eb5b  ldarg.0
0x2eb5c  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2eb61  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Logger()
0x2eb66  dup
0x2eb67  brtrue.s loc_2EB6C
0x2eb69  pop
0x2eb6a  br.s     loc_2EB7A
0x2eb6c  ldloc.s  0xA
0x2eb6e  ldloc.s  0xB
0x2eb70  call     T0x2B000010
0x2eb75  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2eb7a  ldarg.0
0x2eb7b  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2eb80  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Telemetry()
0x2eb85  dup
0x2eb86  brtrue.s loc_2EB8B
0x2eb88  pop
0x2eb89  br.s     loc_2EBA0
0x2eb8b  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ElevationGetWindowHandleFaultEvent
0x2eb90  ldloc.s  0xB
0x2eb92  ldnull
0x2eb93  ldloc.s  0xA
0x2eb95  ldnull
0x2eb96  ldc.i4.0
0x2eb97  ldnull
0x2eb98  ldc.i4.0
0x2eb99  ldnull
0x2eb9a  ldc.i4.0
0x2eb9b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x2eba0  leave.s  loc_2EBA2
0x2eba2  ldarg.1
0x2eba3  ldnull
0x2eba4  ldloc.0
0x2eba5  ldarg.0
0x2eba6  ldfld    string Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::activityId
0x2ebab  ldloc.2
0x2ebac  ldloc.3
0x2ebad  ldloc.s  4
0x2ebaf  ldloc.s  5
0x2ebb1  ldloc.s  6
0x2ebb3  ldloc.s  7
0x2ebb5  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.ElevateOptions::.ctor(string pipeName, string pipeSecret, int32 pid, string activityId, string serializedSession, string locale, string campaignId, bool passive, bool quiet, int64 handle)
0x2ebba  ldc.i4.1
0x2ebbb  call     T0x2B000225
0x2ebc0  stloc.s  8
0x2ebc2  ldloc.1
0x2ebc3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IChildProcess::get_StartInfo()
0x2ebc8  ldloc.s  8
0x2ebca  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessStartInfo::set_Arguments(string)
0x2ebcf  ldloc.1
0x2ebd0  callvirt instance bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess::Start()
0x2ebd5  pop
0x2ebd6  ldloc.1
0x2ebd7  stloc.s  0xC
0x2ebd9  leave    loc_2EC89
0x2ebde  isinst   [System]System.ComponentModel.Win32Exception
0x2ebe3  dup
0x2ebe4  brtrue.s loc_2EBEA
0x2ebe6  pop
0x2ebe7  ldc.i4.0
0x2ebe8  br.s     loc_2EBFD
0x2ebea  stloc.s  0xD
0x2ebec  ldloc.s  0xD
0x2ebee  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x2ebf3  ldc.i4   0x4C7
0x2ebf8  ceq
0x2ebfa  ldc.i4.0
0x2ebfb  cgt.un
0x2ebfd  endfilter
0x2ebff  pop
0x2ec00  ldarg.0
0x2ec01  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2ec06  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Logger()
0x2ec0b  dup
0x2ec0c  brtrue.s loc_2EC11
0x2ec0e  pop
0x2ec0f  br.s     loc_2EC2C
0x2ec11  ldstr    aTheUserHasCanc// "The user has canceled the UAC elevation"...
0x2ec16  ldloc.s  0xD
0x2ec18  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ec1d  call     string [mscorlib]System.String::Concat(string, string)
0x2ec22  call     T0x2B000010
0x2ec27  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2ec2c  ldloc.s  0xD
0x2ec2e  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x2ec33  ldloc.s  0xD
0x2ec35  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ec3a  ldloc.s  0xD
0x2ec3c  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x2ec41  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Pipe.PipeInitializationException::.ctor(int32 hResult, string message, int32 nativeErrorCode)
0x2ec46  throw
0x2ec47  stloc.s  0xE
0x2ec49  ldarg.0
0x2ec4a  ldfld    class Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.ElevatingRpcServerConnector::serviceOptions
0x2ec4f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.Rpc.Connectors.RpcConnectorServiceOptions::get_Logger()
0x2ec54  dup
0x2ec55  brtrue.s loc_2EC5A
0x2ec57  pop
0x2ec58  br.s     loc_2EC75
0x2ec5a  ldstr    aThereWasAnErro// "There was an error while starting the p"...
0x2ec5f  ldloc.s  0xE
0x2ec61  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ec66  call     string [mscorlib]System.String::Concat(string, string)
0x2ec6b  call     T0x2B000010
0x2ec70  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2ec75  ldloc.s  0xE
0x2ec77  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x2ec7c  ldloc.s  0xE
0x2ec7e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ec83  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Pipe.PipeInitializationException::.ctor(int32 hResult, string message)
0x2ec88  throw
0x2ec89  ldloc.s  0xC
0x2ec8b  ret
```
