# Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::TrySaveInstallerTelemetryContext

- ea: `0x410e0`
- end: `0x4119d`
- name: `Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerUpdater::TrySaveInstallerTelemetryContext`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7d2b0`

## callees

- `0x22300`
- `0x2c4a0`
- `0x2c4b0`
- `0x2c550`
- `0x3dbc0`
- `0x40b30`
- `0x410e0`

## string_xrefs

- `0x410f1`: `Saving telemetry context subdirectory: `
- `0x4118b`: `Failed to create an installer telemetry context serializer and serialize.`

## pseudocode

```c

```

## disassembly

```asm
0x410e0  ldarg.0
0x410e1  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x410e6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x410eb  dup
0x410ec  brtrue.s loc_410F1
0x410ee  pop
0x410ef  br.s     loc_41106
0x410f1  ldstr    aSavingTelemetr// "Saving telemetry context subdirectory: "
0x410f6  ldarg.1
0x410f7  call     string [mscorlib]System.String::Concat(string, string)
0x410fc  call     T0x2B000010
0x41101  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x41106  nop
0x41107  ldarg.0
0x41108  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x4110d  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.InstallerTelemetryContextSerializer::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x41112  ldarg.0
0x41113  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x41118  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x4111d  ldarg.0
0x4111e  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x41123  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_FileSystem()
0x41128  ldarg.1
0x41129  call     string Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::GetTelemetryContextFilePath(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem fileSystem, string contextGuid)
0x4112e  ldarg.2
0x4112f  call     T0x2B00029D
0x41134  leave.s  loc_4119C
0x41136  stloc.0
0x41137  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x4113c  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SaveTelemetryContextGuidNullProperty
0x41141  stloc.2
0x41142  dup
0x41143  ldloc.2
0x41144  ldarg.3
0x41145  box      [mscorlib]System.Boolean
0x4114a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4114f  stloc.1
0x41150  ldarg.0
0x41151  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x41156  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Telemetry()
0x4115b  dup
0x4115c  brtrue.s loc_41161
0x4115e  pop
0x4115f  br.s     loc_41179
0x41161  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::SaveTelemetryContextFailEvent
0x41166  ldloc.0
0x41167  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4116c  ldloc.1
0x4116d  ldloc.0
0x4116e  ldnull
0x4116f  ldc.i4.0
0x41170  ldnull
0x41171  ldc.i4.0
0x41172  ldnull
0x41173  ldc.i4.0
0x41174  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x41179  ldarg.0
0x4117a  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions Microsoft.VisualStudio.Setup.Installer.Installer.UnelevatedInstallerBase::get_ServiceOptions()
0x4117f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.InstallerServiceOptions::get_Logger()
0x41184  dup
0x41185  brtrue.s loc_4118A
0x41187  pop
0x41188  br.s     loc_4119A
0x4118a  ldloc.0
0x4118b  ldstr    aFailedToCreate_2// "Failed to create an installer telemetry"...
0x41190  call     T0x2B000010
0x41195  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x4119a  leave.s  loc_4119C
0x4119c  ret
```
