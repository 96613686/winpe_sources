# Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::Handle

- ea: `0x54b80`
- end: `0x54c82`
- name: `Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::Handle`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x9330`
- `0xcd80`
- `0xcd90`
- `0xe180`
- `0x2cb90`
- `0x2cbc0`
- `0x2cbd0`
- `0x54b80`

## string_xrefs

- `0x54bc1`: `OpenUrlCommand`
- `0x54bb4`: `{0} executed. Uri: {1}, LinkId: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x54b80  ldarg.1
0x54b81  ldstr    aUri_0// "uri"
0x54b86  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNull(object, string)
0x54b8b  ldarg.0
0x54b8c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::serviceOptions
0x54b91  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions::get_ProcessService()
0x54b96  ldarg.1
0x54b97  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x54b9c  ldnull
0x54b9d  call     class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcess Microsoft.VisualStudio.Setup.Installer.CommonExtensions::OpenWithExplorer(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IProcessService processService, string path, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem)
0x54ba2  stloc.0
0x54ba3  ldarg.0
0x54ba4  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::serviceOptions
0x54ba9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions::get_Logger()
0x54bae  dup
0x54baf  brtrue.s loc_54BB4
0x54bb1  pop
0x54bb2  br.s     loc_54BDE
0x54bb4  ldstr    a0ExecutedUri1L// "{0} executed. Uri: {1}, LinkId: {2}"
0x54bb9  ldc.i4.3
0x54bba  newarr   [mscorlib]System.Object
0x54bbf  dup
0x54bc0  ldc.i4.0
0x54bc1  ldstr    aOpenurlcommand_0// "OpenUrlCommand"
0x54bc6  stelem.ref
0x54bc7  dup
0x54bc8  ldc.i4.1
0x54bc9  ldarg.1
0x54bca  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x54bcf  stelem.ref
0x54bd0  dup
0x54bd1  ldc.i4.2
0x54bd2  ldarg.1
0x54bd3  callvirt instance string Microsoft.VisualStudio.Setup.Installer.RichUri::get_LinkId()
0x54bd8  stelem.ref
0x54bd9  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x54bde  ldarg.0
0x54bdf  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::serviceOptions
0x54be4  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions::get_Telemetry()
0x54be9  stloc.1
0x54bea  ldloc.1
0x54beb  brfalse  loc_54C75
0x54bf0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x54bf5  dup
0x54bf6  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::InnerText
0x54bfb  ldarg.1
0x54bfc  callvirt instance string Microsoft.VisualStudio.Setup.Installer.RichUri::get_InnerText()
0x54c01  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x54c06  dup
0x54c07  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::LinkId
0x54c0c  ldarg.1
0x54c0d  callvirt instance string Microsoft.VisualStudio.Setup.Installer.RichUri::get_LinkId()
0x54c12  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x54c17  stloc.2
0x54c18  ldarg.1
0x54c19  callvirt instance string [System]System.Uri::get_Scheme()
0x54c1e  ldsfld   string [System]System.Uri::UriSchemeHttps
0x54c23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54c28  brtrue.s loc_54C3C
0x54c2a  ldarg.1
0x54c2b  callvirt instance string [System]System.Uri::get_Scheme()
0x54c30  ldsfld   string [System]System.Uri::UriSchemeHttp
0x54c35  call     bool [mscorlib]System.String::op_Equality(string, string)
0x54c3a  brfalse.s loc_54C4D
0x54c3c  ldloc.2
0x54c3d  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::AbsoluteUri
0x54c42  ldarg.1
0x54c43  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x54c48  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x54c4d  ldloc.1
0x54c4e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.LegacyInstallerTelemetryConstants::ClickedLink
0x54c53  ldloc.2
0x54c54  ldnull
0x54c55  ldc.i4.0
0x54c56  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x54c5b  ldloc.1
0x54c5c  ldarg.0
0x54c5d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions Microsoft.VisualStudio.Setup.Installer.Commands.OpenUrlCommand::serviceOptions
0x54c62  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.OpenUrlCommandServiceOptions::get_Logger()
0x54c67  ldc.i4.s 0xD
0x54c69  ldc.i4.0
0x54c6a  ldarg.1
0x54c6b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x54c70  call     void Microsoft.VisualStudio.Setup.Installer.UiTelemetry::WriteButtonEvent(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry telemetry, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger logger, valuetype Microsoft.VisualStudio.Setup.Installer.ButtonName buttonName, valuetype Microsoft.VisualStudio.Setup.Installer.UserExecuteAction action, [opt] string message)
0x54c75  leave.s  loc_54C81
0x54c77  ldloc.0
0x54c78  brfalse.s loc_54C80
0x54c7a  ldloc.0
0x54c7b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54c80  endfinally
0x54c81  ret
```
