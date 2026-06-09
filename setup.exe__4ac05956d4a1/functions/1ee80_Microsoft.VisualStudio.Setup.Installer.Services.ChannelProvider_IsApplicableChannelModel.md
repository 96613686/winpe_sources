# Microsoft.VisualStudio.Setup.Installer.Services.ChannelProvider::IsApplicableChannelModel

- ea: `0x1ee80`
- end: `0x1ef0b`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.ChannelProvider::IsApplicableChannelModel`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6c030`

## callees

- `0x1ee80`
- `0x1ef10`
- `0x2b8e0`
- `0x363c0`
- `0x363d0`
- `0x36450`
- `0x3b590`
- `0x3b5a0`
- `0x3b5b0`

## string_xrefs

- `0x1eeca`: `Channel '{0}' already has product '{1};{2}' installed. Mark it as not applicable.`

## pseudocode

```c

```

## disassembly

```asm
0x1ee80  ldarg.1
0x1ee81  brtrue.s loc_1EE85
0x1ee83  ldc.i4.0
0x1ee84  ret
0x1ee85  ldarg.1
0x1ee86  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x1ee8b  ldarg.2
0x1ee8c  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x1ee91  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x1ee96  call     bool [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Extensions::Matches(class [System]System.Uri, class [System]System.Uri)
0x1ee9b  brfalse.s loc_1EE9F
0x1ee9d  ldc.i4.1
0x1ee9e  ret
0x1ee9f  ldarg.0
0x1eea0  ldarg.2
0x1eea1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x1eea6  ldarg.1
0x1eea7  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x1eeac  ldarg.2
0x1eead  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_ProductArch()
0x1eeb2  call     instance bool Microsoft.VisualStudio.Setup.Installer.Services.ChannelProvider::HasExistingProduct(string productId, class [System]System.Uri channelUri, string productArch)
0x1eeb7  brfalse.s loc_1EEF7
0x1eeb9  ldarg.0
0x1eeba  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelProviderServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.ChannelProvider::serviceOptions
0x1eebf  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelProviderServiceOptions::get_Logger()
0x1eec4  dup
0x1eec5  brtrue.s loc_1EECA
0x1eec7  pop
0x1eec8  br.s     loc_1EEF5
0x1eeca  ldstr    aChannel0Alread// "Channel '{0}' already has product '{1};"...
0x1eecf  ldc.i4.3
0x1eed0  newarr   [mscorlib]System.Object
0x1eed5  dup
0x1eed6  ldc.i4.0
0x1eed7  ldarg.1
0x1eed8  callvirt instance class [System]System.Uri Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_UpdateUri()
0x1eedd  stelem.ref
0x1eede  dup
0x1eedf  ldc.i4.1
0x1eee0  ldarg.2
0x1eee1  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x1eee6  stelem.ref
0x1eee7  dup
0x1eee8  ldc.i4.2
0x1eee9  ldarg.2
0x1eeea  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_ProductArch()
0x1eeef  stelem.ref
0x1eef0  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x1eef5  ldc.i4.0
0x1eef6  ret
0x1eef7  ldarg.1
0x1eef8  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel::get_IsRetired()
0x1eefd  brtrue.s loc_1EF09
0x1eeff  ldarg.1
0x1ef00  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel::get_IsExpired()
0x1ef05  ldc.i4.0
0x1ef06  ceq
0x1ef08  ret
0x1ef09  ldc.i4.0
0x1ef0a  ret
```
