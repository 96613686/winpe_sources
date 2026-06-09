# Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SetBaseSharedProperties

- ea: `0xd8e0`
- end: `0xda29`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::SetBaseSharedProperties`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xd0f0`

## callees

- `0xb2c0`
- `0xd8e0`
- `0xda30`
- `0x219c0`
- `0x219d0`
- `0x219e0`
- `0x21a10`
- `0x21a20`
- `0x599d0`
- `0x59a90`
- `0x59ab0`
- `0x5a300`

## string_xrefs

- `0xd9c8`: `service`

## pseudocode

```c

```

## disassembly

```asm
0xd8e0  ldarg.2
0xd8e1  ldsfld   string SharedProperties::SourceProperty
0xd8e6  ldstr    aWpf// "WPF"
0xd8eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd8f0  ldarg.2
0xd8f1  ldsfld   string SharedProperties::LocaleProperty
0xd8f6  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xd8fb  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Threading.Thread::get_CurrentUICulture()
0xd900  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd905  ldarg.2
0xd906  ldsfld   string SharedProperties::InstallerVersionProperty
0xd90b  call     string Microsoft.VisualStudio.Setup.Installer.InstallerInfo::get_InstallerVersion()
0xd910  dup
0xd911  brtrue.s loc_D919
0xd913  pop
0xd914  ldsfld   string [mscorlib]System.String::Empty
0xd919  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd91e  ldarg.0
0xd91f  brtrue.s loc_D924
0xd921  ldnull
0xd922  br.s     loc_D92A
0xd924  ldarg.0
0xd925  call     instance string Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_ActivityId()
0xd92a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xd92f  brfalse.s loc_D943
0xd931  ldarg.2
0xd932  ldsfld   string SharedProperties::StartMethodProperty
0xd937  ldstr    aDirect// "direct"
0xd93c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd941  br.s     loc_D953
0xd943  ldarg.2
0xd944  ldsfld   string SharedProperties::StartMethodProperty
0xd949  ldstr    aIndirect// "indirect"
0xd94e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd953  ldarg.2
0xd954  ldsfld   string SharedProperties::ActivityIdProperty
0xd959  ldarg.1
0xd95a  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_ActivityId()
0xd95f  dup
0xd960  brtrue.s loc_D968
0xd962  pop
0xd963  ldsfld   string [mscorlib]System.String::Empty
0xd968  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd96d  ldarg.2
0xd96e  ldsfld   string SharedProperties::CampaignProperty
0xd973  ldarg.1
0xd974  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_CampaignId()
0xd979  dup
0xd97a  brtrue.s loc_D982
0xd97c  pop
0xd97d  ldsfld   string [mscorlib]System.String::Empty
0xd982  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd987  ldarg.2
0xd988  ldsfld   string SharedProperties::PassiveProperty
0xd98d  ldarg.1
0xd98e  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Passive()
0xd993  box      [mscorlib]System.Boolean
0xd998  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd99d  ldarg.2
0xd99e  ldsfld   string SharedProperties::QuietProperty
0xd9a3  ldarg.1
0xd9a4  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_Quiet()
0xd9a9  box      [mscorlib]System.Boolean
0xd9ae  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd9b3  ldarg.2
0xd9b4  ldsfld   string SharedProperties::ProcessType
0xd9b9  ldarg.1
0xd9ba  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService::get_IsService()
0xd9bf  brtrue.s loc_D9C8
0xd9c1  ldstr    aUi// "ui"
0xd9c6  br.s     loc_D9CD
0xd9c8  ldstr    aService// "service"
0xd9cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd9d2  ldarg.0
0xd9d3  brfalse.s loc_DA21
0xd9d5  ldarg.2
0xd9d6  ldsfld   string SharedProperties::ForceProperty
0xd9db  ldarg.0
0xd9dc  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_Force()
0xd9e1  box      [mscorlib]System.Boolean
0xd9e6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xd9eb  ldarg.2
0xd9ec  ldsfld   string SharedProperties::NoWebProperty
0xd9f1  ldarg.0
0xd9f2  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.NonVerbOptions::get_NoWeb()
0xd9f7  box      [mscorlib]System.Boolean
0xd9fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xda01  ldarg.0
0xda02  isinst   Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions
0xda07  stloc.0
0xda08  ldloc.0
0xda09  brfalse.s loc_DA21
0xda0b  ldarg.2
0xda0c  ldsfld   string SharedProperties::UpdateFromVSProperty
0xda11  ldloc.0
0xda12  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.CommandLine.Options.UpdateOptions::get_UpdateFromVS()
0xda17  box      [mscorlib]System.Boolean
0xda1c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0xda21  ldarg.1
0xda22  ldarg.2
0xda23  call     void Microsoft.VisualStudio.Setup.Installer.InstallerTelemetry::AddUserSharedProperties(class Microsoft.VisualStudio.Setup.Installer.Services.IInstallerSettingsService installerSettingsService, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> sharedTelemetryProperties)
0xda28  ret
```
