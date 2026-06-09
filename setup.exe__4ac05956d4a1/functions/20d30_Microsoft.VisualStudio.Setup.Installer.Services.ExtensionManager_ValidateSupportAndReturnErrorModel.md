# Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateSupportAndReturnErrorModel

- ea: `0x20d30`
- end: `0x20da2`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateSupportAndReturnErrorModel`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x20540`
- `0x6e680`

## callees

- `0x9310`
- `0x209b0`
- `0x20d30`
- `0x20db0`

## string_xrefs

- `0x20d83`: `Extension is not supported: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x20d30  ldarg.0
0x20d31  ldarg.1
0x20d32  ldarg.2
0x20d33  ldarg.3
0x20d34  call     instance valuetype [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.SupportedExtensionResult Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::ValidateExtensionIsSupported(class [System]System.Uri extensionUri, class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.ExtensionContents extensionContents, class Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductModel product)
0x20d39  stloc.0
0x20d3a  ldloc.0
0x20d3b  ldc.i4.2
0x20d3c  beq.s    loc_20D42
0x20d3e  ldloc.0
0x20d3f  ldc.i4.1
0x20d40  bne.un.s loc_20DA0
0x20d42  ldarg.s  4
0x20d44  brfalse.s loc_20D57
0x20d46  ldarg.s  4
0x20d48  ldsfld   string Extensions::ResultProperty
0x20d4d  ldstr    aBlock// "Block"
0x20d52  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x20d57  ldarg.s  4
0x20d59  brfalse.s loc_20D6D
0x20d5b  ldarg.s  4
0x20d5d  ldsfld   string Extensions::InvalidExtensionProperty
0x20d62  ldc.i4.1
0x20d63  box      [mscorlib]System.Boolean
0x20d68  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x20d6d  ldarg.s  4
0x20d6f  brfalse.s loc_20D83
0x20d71  ldarg.s  4
0x20d73  ldsfld   string Extensions::InvalidExtensionTypeProperty
0x20d78  ldloc.0
0x20d79  box      [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.SupportedExtensionResult
0x20d7e  call     void Microsoft.VisualStudio.Setup.Installer.CommonExtensions::SetProperty(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, string key, object value)
0x20d83  ldstr    aExtensionIsNot// "Extension is not supported: {0}"
0x20d88  ldloc.0
0x20d89  box      [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Extension.SupportedExtensionResult
0x20d8e  call     string [mscorlib]System.String::Format(string, object)
0x20d93  stloc.1
0x20d94  ldarg.0
0x20d95  ldarg.s  4
0x20d97  ldarg.1
0x20d98  ldc.i4.4
0x20d99  ldloc.1
0x20d9a  call     instance class Microsoft.VisualStudio.Setup.Installer.ExtensionModelSummary Microsoft.VisualStudio.Setup.Installer.Services.ExtensionManager::RecordFullModelCreationFailureAndReturn(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation telemetryOperation, class [System]System.Uri extensionUri, valuetype Microsoft.VisualStudio.Setup.Installer.ExtensionModelErrorState errorState, [opt] string additionalMessage)
0x20d9f  ret
0x20da0  ldnull
0x20da1  ret
```
