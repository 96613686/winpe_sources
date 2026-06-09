# Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::ShutdownExtensionValidationFailureInPassiveOrQuietMode

- ea: `0x3dae0`
- end: `0x3db4f`
- name: `Microsoft.VisualStudio.Setup.Installer.Utilities.Utilities::ShutdownExtensionValidationFailureInPassiveOrQuietMode`
- size: `111`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x80ca0`
- `0x81e20`
- `0x92210`

## callees

- `0xa5d0`
- `0xaf30`
- `0x229c0`
- `0x3dae0`

## string_xrefs

- `0x3dafa`: `allowUnsignedExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x3dae0  ldarg.1
0x3dae1  call     bool Microsoft.VisualStudio.Setup.Installer.Extensions::IsQuietOrPassive(class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService installerSettings)
0x3dae6  brfalse.s loc_3DB4E
0x3dae8  ldarg.0
0x3dae9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel> Microsoft.VisualStudio.Setup.Installer.ExtensionsSignatureValidationResult::get_InvalidlySignedExtensions()
0x3daee  call     T0x2B00004B
0x3daf3  brtrue.s loc_3DB06
0x3daf5  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_PassiveOrQuietModeUnsignedExtensionsFailureMessage_Args1()
0x3dafa  ldstr    aAllowunsignede// "allowUnsignedExtensions"
0x3daff  call     string [mscorlib]System.String::Format(string, object)
0x3db04  br.s     loc_3DB44
0x3db06  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_PassiveOrQuietModeExtensionsSignatureValidationFailureMessage_Args1()
0x3db0b  call     string [mscorlib]System.Environment::get_NewLine()
0x3db10  ldarg.0
0x3db11  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel> Microsoft.VisualStudio.Setup.Installer.ExtensionsSignatureValidationResult::get_InvalidlySignedExtensions()
0x3db16  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel, string> <>c::<>9__14_0
0x3db1b  dup
0x3db1c  brtrue.s loc_3DB35
0x3db1e  pop
0x3db1f  ldsfld   class <>c <>c::<>9
0x3db24  ldftn    instance string <>c::<ShutdownExtensionValidationFailureInPassiveOrQuietMode>b__14_0(class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel x)
0x3db2a  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel, string>::.ctor(object, native int)
0x3db2f  dup
0x3db30  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Installer.Models.Selectables.IExtensionModel, string> <>c::<>9__14_0
0x3db35  call     T0x2B00027B
0x3db3a  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x3db3f  call     string [mscorlib]System.String::Format(string, object)
0x3db44  stloc.0
0x3db45  ldarg.2
0x3db46  ldc.i4.1
0x3db47  ldloc.0
0x3db48  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Services.IShutdownRequestService::Shutdown(int32 exitCode, string message)
0x3db4d  ret
0x3db4e  ret
```
