# Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::GetEmbeddedExtension

- ea: `0x20540`
- end: `0x205e8`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::GetEmbeddedExtension`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x205f0`

## callees

- `0x9d40`
- `0x20540`
- `0x209b0`
- `0x20d30`
- `0x2bcb0`
- `0x6c7f0`
- `0x6c890`

## string_xrefs

- `0x20565`: `Embedded extension at path {0} is not supported`
- `0x20592`: `The provided embedded extension {0} does not have a proper Component authoring.`
- `0x205af`: `Successfully added embedded extension.`
- `0x205d2`: `Successfully added embedded extension at {0}`

## pseudocode

```c

```

## disassembly

```asm
0x20540  ldarg.0
0x20541  ldarg.1
0x20542  ldarg.2
0x20543  callvirt instance class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents ExtensionContentsSummary::get_ExtensionContents()
0x20548  ldarg.3
0x20549  ldarg.s  4
0x2054b  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateSupportAndReturnErrorModel(class [System]System.Uri, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents extensionUri, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel extensionContents, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation product)
0x20550  stloc.0
0x20551  ldloc.0
0x20552  brfalse.s loc_20580
0x20554  ldarg.0
0x20555  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x2055a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x2055f  dup
0x20560  brtrue.s loc_20565
0x20562  pop
0x20563  br.s     loc_20579
0x20565  ldstr    aEmbeddedExtens// "Embedded extension at path {0} is not s"...
0x2056a  ldc.i4.1
0x2056b  newarr   [mscorlib]System.Object
0x20570  dup
0x20571  ldc.i4.0
0x20572  ldarg.1
0x20573  stelem.ref
0x20574  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x20579  ldloc.0
0x2057a  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::get_ErrorState()
0x2057f  ret
0x20580  ldarg.2
0x20581  callvirt instance class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> ExtensionContentsSummary::get_ParsedComponents()
0x20586  stloc.1
0x20587  ldloc.1
0x20588  brfalse.s loc_20592
0x2058a  ldloc.1
0x2058b  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity>::get_Count()
0x20590  brtrue.s loc_205AF
0x20592  ldstr    aTheProvidedEmb// "The provided embedded extension {0} doe"...
0x20597  ldarg.1
0x20598  call     string [mscorlib]System.String::Format(string, object)
0x2059d  stloc.3
0x2059e  ldarg.0
0x2059f  ldarg.s  4
0x205a1  ldarg.1
0x205a2  ldc.i4.4
0x205a3  ldloc.3
0x205a4  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::RecordFullModelCreationFailureAndReturn(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [System]System.Uri extensionUri, valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState errorState, [opt] string additionalMessage)
0x205a9  callvirt instance valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary::get_ErrorState()
0x205ae  ret
0x205af  ldstr    aSuccessfullyAd// "Successfully added embedded extension."
0x205b4  stloc.2
0x205b5  ldarg.s  4
0x205b7  brfalse.s loc_205C1
0x205b9  ldarg.s  4
0x205bb  ldloc.2
0x205bc  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x205c1  ldarg.0
0x205c2  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ExtensionManagerServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::serviceOptions
0x205c7  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommonInstallerServiceOptions::get_Logger()
0x205cc  dup
0x205cd  brtrue.s loc_205D2
0x205cf  pop
0x205d0  br.s     loc_205E6
0x205d2  ldstr    aSuccessfullyAd_0// "Successfully added embedded extension a"...
0x205d7  ldc.i4.1
0x205d8  newarr   [mscorlib]System.Object
0x205dd  dup
0x205de  ldc.i4.0
0x205df  ldarg.1
0x205e0  stelem.ref
0x205e1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x205e6  ldc.i4.0
0x205e7  ret
```
