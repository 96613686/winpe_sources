# Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::GetInstallerUpdateForNoWeb

- ea: `0x28710`
- end: `0x28a1f`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::GetInstallerUpdateForNoWeb`
- size: `783`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x282a0`

## callees

- `0xb2b0`
- `0xb300`
- `0x28710`
- `0x2cec0`
- `0x2cf50`
- `0x2cf60`
- `0x36710`
- `0x36740`
- `0x36790`
- `0x367b0`

## string_xrefs

- `0x28721`: `Since noWeb is enabled, updates from latestInstaller feed and channelManager feed are not checked.`
- `0x287be`: `layoutPath is `
- `0x28817`: `Current installer version {0}`
- `0x28882`: `Since layout OPC version is greater than layout, installer needs update.`
- `0x2895a`: `Failed to get installer update information for noWeb. `
- `0x289bd`: `Error happened while trying to get installer update information for noWeb.`

## pseudocode

```c

```

## disassembly

```asm
0x28710  ldarg.0
0x28711  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x28716  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x2871b  dup
0x2871c  brtrue.s loc_28721
0x2871e  pop
0x2871f  br.s     loc_28730
0x28721  ldstr    aSinceNowebIsEn// "Since noWeb is enabled, updates from la"...
0x28726  call     T0x2B000010
0x2872b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x28730  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x28735  stloc.0
0x28736  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::.ctor()
0x2873b  stloc.1
0x2873c  ldarg.0
0x2873d  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x28742  call     class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.InstallerInfo::GetRunningSetupPackageVersion([opt] class [mscorlib]System.IServiceProvider services)
0x28747  dup
0x28748  brtrue.s loc_28755
0x2874a  pop
0x2874b  call     string Microsoft.VisualStudio.Setup.Installer.InstallerInfo::get_SetupPackageVersion()
0x28750  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x28755  stloc.2
0x28756  ldarg.1
0x28757  dup
0x28758  brtrue.s loc_2876B
0x2875a  pop
0x2875b  ldarg.0
0x2875c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x28761  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_ChannelManager()
0x28766  callvirt instance string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::get_InstallLayoutPath()
0x2876b  stloc.3
0x2876c  ldloc.3
0x2876d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x28772  brtrue   loc_288DF
0x28777  ldloc.3
0x28778  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.BootstrapperConstants::VsInstallerVersionFilename
0x2877d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x28782  stloc.s  4
0x28784  ldarg.0
0x28785  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x2878a  ldloc.s  4
0x2878c  ldnull
0x2878d  newobj   instance void [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ClientVersionFile::.ctor(class [mscorlib]System.IServiceProvider, string, class [mscorlib]System.IO.Stream)
0x28792  stloc.s  5
0x28794  ldloc.0
0x28795  ldsfld   string InstallerUpdateInfo::LayoutOpcVersionProperty
0x2879a  ldloc.s  5
0x2879c  brtrue.s loc_287A1
0x2879e  ldnull
0x2879f  br.s     loc_287A8
0x287a1  ldloc.s  5
0x287a3  call     instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ClientVersionFile::get_InstallerVersion()
0x287a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x287ad  ldarg.0
0x287ae  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x287b3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x287b8  dup
0x287b9  brtrue.s loc_287BE
0x287bb  pop
0x287bc  br.s     loc_287D3
0x287be  ldstr    aLayoutpathIs// "layoutPath is "
0x287c3  ldloc.3
0x287c4  call     string [mscorlib]System.String::Concat(string, string)
0x287c9  call     T0x2B000010
0x287ce  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x287d3  ldarg.0
0x287d4  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x287d9  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x287de  dup
0x287df  brtrue.s loc_287E4
0x287e1  pop
0x287e2  br.s     loc_28806
0x287e4  ldstr    aOpcVersionInLa// "OPC version in layout is {0}"
0x287e9  ldloc.s  5
0x287eb  brtrue.s loc_287F0
0x287ed  ldnull
0x287ee  br.s     loc_287F7
0x287f0  ldloc.s  5
0x287f2  call     instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ClientVersionFile::get_InstallerVersion()
0x287f7  call     string [mscorlib]System.String::Format(string, object)
0x287fc  call     T0x2B000010
0x28801  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x28806  ldarg.0
0x28807  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x2880c  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x28811  dup
0x28812  brtrue.s loc_28817
0x28814  pop
0x28815  br.s     loc_2882C
0x28817  ldstr    aCurrentInstall// "Current installer version {0}"
0x2881c  ldloc.2
0x2881d  call     string [mscorlib]System.String::Format(string, object)
0x28822  call     T0x2B000010
0x28827  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x2882c  ldloc.s  5
0x2882e  brfalse  loc_288DF
0x28833  ldloc.s  5
0x28835  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ClientVersionFile::get_InstallerVersion()
0x2883a  ldloc.2
0x2883b  call     bool [mscorlib]System.Version::op_GreaterThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x28840  brfalse  loc_288DF
0x28845  ldloc.3
0x28846  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LayoutConstants::BootstrapperStaticName
0x2884b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x28850  stloc.s  6
0x28852  ldloc.3
0x28853  ldsfld   string [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.LayoutConstants::InstallerOPCFile
0x28858  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x2885d  stloc.s  7
0x2885f  ldc.i4.1
0x28860  ldloc.s  6
0x28862  ldloc.s  5
0x28864  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.ClientVersionFile::get_InstallerVersion()
0x28869  ldloc.s  7
0x2886b  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::.ctor(bool isUpdateRequired, string bootstrapperUrl, class [mscorlib]System.Version opcVersion, [opt] string opcUrl)
0x28870  stloc.1
0x28871  ldarg.0
0x28872  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x28877  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x2887c  dup
0x2887d  brtrue.s loc_28882
0x2887f  pop
0x28880  br.s     loc_28891
0x28882  ldstr    aSinceLayoutOpc// "Since layout OPC version is greater tha"...
0x28887  call     T0x2B000010
0x2888c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x28891  ldarg.0
0x28892  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x28897  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x2889c  dup
0x2889d  brtrue.s loc_288A2
0x2889f  pop
0x288a0  br.s     loc_288B8
0x288a2  ldstr    aOpcUrl// "OPC Url - "
0x288a7  ldloc.s  7
0x288a9  call     string [mscorlib]System.String::Concat(string, string)
0x288ae  call     T0x2B000010
0x288b3  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x288b8  ldarg.0
0x288b9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x288be  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x288c3  dup
0x288c4  brtrue.s loc_288C9
0x288c6  pop
0x288c7  br.s     loc_288DF
0x288c9  ldstr    aBootstrapperUr// "Bootstrapper Url - "
0x288ce  ldloc.s  6
0x288d0  call     string [mscorlib]System.String::Concat(string, string)
0x288d5  call     T0x2B000010
0x288da  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x288df  ldloc.0
0x288e0  ldsfld   string InstallerUpdateInfo::CurrentClientVersionProperty
0x288e5  ldloc.2
0x288e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x288eb  ldloc.0
0x288ec  ldsfld   string InstallerUpdateInfo::ChannelManagerSuggestingUpdateProperty
0x288f1  ldarg.0
0x288f2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x288f7  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_ChannelManager()
0x288fc  dup
0x288fd  brtrue.s loc_2890C
0x288ff  pop
0x28900  ldloca.s 8
0x28902  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x28908  ldloc.s  8
0x2890a  br.s     loc_28916
0x2890c  callvirt instance bool [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::get_IsEngineUpdateRequired()
0x28911  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x28916  box      valuetype [mscorlib]System.Nullable`1<bool>
0x2891b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28920  ldloc.0
0x28921  ldsfld   string InstallerUpdateInfo::ChannelManagerSuggestedVersionProperty
0x28926  ldarg.0
0x28927  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x2892c  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_ChannelManager()
0x28931  dup
0x28932  brtrue.s loc_28938
0x28934  pop
0x28935  ldnull
0x28936  br.s     loc_2893D
0x28938  callvirt instance class [mscorlib]System.Version [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.IChannelManager::get_UpdateClientVersion()
0x2893d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28942  leave    loc_289D5
0x28947  stloc.s  9
0x28949  ldarg.0
0x2894a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x2894f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Logger()
0x28954  dup
0x28955  brtrue.s loc_2895A
0x28957  pop
0x28958  br.s     loc_28980
0x2895a  ldstr    aFailedToGetIns// "Failed to get installer update informat"...
0x2895f  ldloc.s  9
0x28961  callvirt instance string [mscorlib]System.Exception::get_Message()
0x28966  call     string [mscorlib]System.String::Concat(string, string)
0x2896b  ldc.i4.1
0x2896c  newarr   [mscorlib]System.Object
0x28971  dup
0x28972  ldc.i4.0
0x28973  ldloc.s  9
0x28975  callvirt instance string [mscorlib]System.Object::ToString()
0x2897a  stelem.ref
0x2897b  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x28980  ldloc.0
0x28981  ldsfld   string InstallerUpdateInfo::UpdateRequiredProperty
0x28986  ldloc.1
0x28987  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_IsUpdateRequired()
0x2898c  box      [mscorlib]System.Boolean
0x28991  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x28996  ldloc.0
0x28997  ldsfld   string InstallerUpdateInfo::TargetClientVersionProperty
0x2899c  ldloc.1
0x2899d  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcVersion()
0x289a2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x289a7  ldarg.0
0x289a8  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x289ad  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Telemetry()
0x289b2  dup
0x289b3  brtrue.s loc_289B8
0x289b5  pop
0x289b6  br.s     loc_289D0
0x289b8  ldsfld   string InstallerUpdateInfo::UpdateInstallerNowebExceptionEvent
0x289bd  ldstr    aErrorHappenedW// "Error happened while trying to get inst"...
0x289c2  ldloc.0
0x289c3  ldloc.s  9
0x289c5  ldnull
0x289c6  ldc.i4.0
0x289c7  ldnull
0x289c8  ldc.i4.0
0x289c9  ldnull
0x289ca  ldc.i4.0
0x289cb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x289d0  ldloc.1
0x289d1  stloc.s  0xA
0x289d3  leave.s  loc_28A1C
0x289d5  ldloc.0
0x289d6  ldsfld   string InstallerUpdateInfo::UpdateRequiredProperty
0x289db  ldloc.1
0x289dc  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_IsUpdateRequired()
0x289e1  box      [mscorlib]System.Boolean
0x289e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x289eb  ldloc.0
0x289ec  ldsfld   string InstallerUpdateInfo::TargetClientVersionProperty
0x289f1  ldloc.1
0x289f2  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Installer.Models.InstallerUpdateInformationModel::get_OpcVersion()
0x289f7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x289fc  ldarg.0
0x289fd  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.UpdateProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.UpdateProviderService::serviceOptions
0x28a02  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ProductsProviderServiceOptions::get_Telemetry()
0x28a07  dup
0x28a08  brtrue.s loc_28A0D
0x28a0a  pop
0x28a0b  br.s     loc_28A1A
0x28a0d  ldsfld   string InstallerUpdateInfo::UpdateInstallerNowebEvent
0x28a12  ldloc.0
0x28a13  ldnull
0x28a14  ldc.i4.0
0x28a15  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x28a1a  ldloc.1
0x28a1b  ret
0x28a1c  ldloc.s  0xA
0x28a1e  ret
```
