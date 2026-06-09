# Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsCommand::SendOpenSettingsTelemetry

- ea: `0x19f90`
- end: `0x1a00b`
- name: `Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsCommand::SendOpenSettingsTelemetry`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x19f00`

## callees

- `0x19f90`
- `0x2b9d0`
- `0x36440`
- `0x3a840`
- `0x3b590`
- `0x3b5a0`

## string_xrefs

- `0x19fe2`: `UpdateDialog`

## pseudocode

```c

```

## disassembly

```asm
0x19f90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x19f95  ldsfld   string UpdateSettings::ProductIdProperty
0x19f9a  stloc.1
0x19f9b  dup
0x19f9c  ldloc.1
0x19f9d  ldarg.1
0x19f9e  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Id()
0x19fa3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x19fa8  ldsfld   string UpdateSettings::ChannelIdProperty
0x19fad  stloc.2
0x19fae  dup
0x19faf  ldloc.2
0x19fb0  ldarg.1
0x19fb1  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Models.IChannelModel Microsoft.VisualStudio.Setup.Installer.Models.Products.IProductIdentityModel::get_Channel()
0x19fb6  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.IChannelModelSummary::get_Id()
0x19fbb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x19fc0  ldsfld   string UpdateSettings::RemoveOosProperty
0x19fc5  stloc.3
0x19fc6  dup
0x19fc7  ldloc.3
0x19fc8  ldarg.1
0x19fc9  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductBaseModel::get_RemoveOos()
0x19fce  box      [mscorlib]System.Boolean
0x19fd3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x19fd8  ldsfld   string UpdateSettings::SourceProperty
0x19fdd  stloc.s  4
0x19fdf  dup
0x19fe0  ldloc.s  4
0x19fe2  ldstr    aUpdatedialog// "UpdateDialog"
0x19fe7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x19fec  stloc.0
0x19fed  ldarg.0
0x19fee  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerServiceOptions Microsoft.VisualStudio.Setup.Installer.UpdateDialog.Commands.OpenUpdateSettingsCommand::serviceOptions
0x19ff3  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.CommandHandlerBaseServiceOptions::get_Telemetry()
0x19ff8  dup
0x19ff9  brtrue.s loc_19FFD
0x19ffb  pop
0x19ffc  ret
0x19ffd  ldsfld   string UpdateSettings::OpenChangeSettingsEvent
0x1a002  ldloc.0
0x1a003  ldnull
0x1a004  ldc.i4.0
0x1a005  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x1a00a  ret
```
