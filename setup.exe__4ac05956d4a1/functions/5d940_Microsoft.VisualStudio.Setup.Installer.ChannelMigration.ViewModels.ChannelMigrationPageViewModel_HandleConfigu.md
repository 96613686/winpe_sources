# Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::HandleConfigureSelection

- ea: `0x5d940`
- end: `0x5da78`
- name: `Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::HandleConfigureSelection`
- size: `312`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x2d6b0`
- `0x54080`
- `0x5d3c0`
- `0x5d570`
- `0x5d5d0`
- `0x5d600`
- `0x5d640`
- `0x5d6e0`
- `0x5d720`
- `0x5d8b0`
- `0x5d940`
- `0x5da80`

## string_xrefs

- `0x5d9de`: `Configuration`
- `0x5da25`: `Channel Migration Configure Handled`
- `0x5da46`: `Failed to open installation details from channel migration.`
- `0x5da59`: `Failed to open installation details from channel migration.`
- `0x5da60`: `Channel Migration Open Details Error`

## pseudocode

```c

```

## disassembly

```asm
0x5d940  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x5d945  ldsfld   string ChannelMigration::IncludeMarketplaceExtensions
0x5d94a  stloc.2
0x5d94b  dup
0x5d94c  ldloc.2
0x5d94d  ldarg.0
0x5d94e  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_IncludeMarketplaceExtensions()
0x5d953  box      [mscorlib]System.Boolean
0x5d958  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5d95d  ldsfld   string ChannelMigration::IncludeOutOfSupport
0x5d962  stloc.3
0x5d963  dup
0x5d964  ldloc.3
0x5d965  ldarg.0
0x5d966  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_IncludeOutOfSupport()
0x5d96b  box      [mscorlib]System.Boolean
0x5d970  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5d975  ldsfld   string ChannelMigration::MigrateFromInstance
0x5d97a  stloc.s  4
0x5d97c  dup
0x5d97d  ldloc.s  4
0x5d97f  ldarg.0
0x5d980  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_MigrateFromInstance()
0x5d985  box      [mscorlib]System.Boolean
0x5d98a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5d98f  ldsfld   string ChannelMigration::MigrationCandidateCount
0x5d994  stloc.s  5
0x5d996  dup
0x5d997  ldloc.s  5
0x5d999  ldarg.0
0x5d99a  call     instance class [System]System.Collections.ObjectModel.ObservableCollection`1<class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.IInstanceMigrationCandidateViewModel> Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_MigrationCandidateList()
0x5d99f  dup
0x5d9a0  brtrue.s loc_5D9A6
0x5d9a2  pop
0x5d9a3  ldc.i4.0
0x5d9a4  br.s     loc_5D9AB
0x5d9a6  call     instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.IInstanceMigrationCandidateViewModel>::get_Count()
0x5d9ab  box      [mscorlib]System.Int32
0x5d9b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5d9b5  ldsfld   string ChannelMigration::SelectedMigrationCandidateType
0x5d9ba  stloc.s  6
0x5d9bc  dup
0x5d9bd  ldloc.s  6
0x5d9bf  ldarg.0
0x5d9c0  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_NewInstallation()
0x5d9c5  brtrue.s loc_5D9EC
0x5d9c7  ldarg.0
0x5d9c8  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_MigrateFromInstance()
0x5d9cd  brtrue.s loc_5D9E5
0x5d9cf  ldarg.0
0x5d9d0  call     instance bool Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_MigrateFromConfiguration()
0x5d9d5  brtrue.s loc_5D9DE
0x5d9d7  ldstr    aUnexpected// "Unexpected"
0x5d9dc  br.s     loc_5D9F1
0x5d9de  ldstr    aConfiguration// "Configuration"
0x5d9e3  br.s     loc_5D9F1
0x5d9e5  ldstr    aInstance// "Instance"
0x5d9ea  br.s     loc_5D9F1
0x5d9ec  ldstr    aDefault// "Default"
0x5d9f1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5d9f6  stloc.0
0x5d9f7  ldarg.0
0x5d9f8  ldsfld   string ChannelMigration::ChannelMigrationHandleConfigureEvent
0x5d9fd  ldloc.0
0x5d9fe  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::StartTelemetryOperation(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> eventName)
0x5da03  stloc.1
0x5da04  ldarg.0
0x5da05  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::closeCommand
0x5da0a  callvirt instance void Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand::Execute()
0x5da0f  ldarg.0
0x5da10  ldfld    class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Commands.ViewInstallationDetailsCommandArgs> Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::viewInstallationDetailsCommand
0x5da15  ldarg.0
0x5da16  ldloc.1
0x5da17  call     instance class Microsoft.VisualStudio.Setup.Installer.Commands.ViewInstallationDetailsCommandArgs Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::GetInstallationDetailsArgs(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation operation)
0x5da1c  callvirt instance void class Microsoft.VisualStudio.Setup.Installer.Commands.IRelayCommand`1<class Microsoft.VisualStudio.Setup.Installer.Commands.ViewInstallationDetailsCommandArgs>::Execute(var<u1>)
0x5da21  ldloc.1
0x5da22  brfalse.s loc_5DA2F
0x5da24  ldloc.1
0x5da25  ldstr    aChannelMigrati// "Channel Migration Configure Handled"
0x5da2a  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordSuccess(string)
0x5da2f  leave.s  loc_5DA77
0x5da31  stloc.s  7
0x5da33  ldarg.0
0x5da34  call     instance class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ChannelMigrationPageServiceOptions Microsoft.VisualStudio.Setup.Installer.ChannelMigration.ViewModels.ChannelMigrationPageViewModel::get_ServiceOptions()
0x5da39  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.ViewModelBaseServiceOptions::get_Logger()
0x5da3e  dup
0x5da3f  brtrue.s loc_5DA44
0x5da41  pop
0x5da42  br.s     loc_5DA55
0x5da44  ldloc.s  7
0x5da46  ldstr    aFailedToOpenIn// "Failed to open installation details fro"...
0x5da4b  call     T0x2B000010
0x5da50  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x5da55  ldloc.1
0x5da56  brfalse.s loc_5DA6B
0x5da58  ldloc.1
0x5da59  ldstr    aFailedToOpenIn// "Failed to open installation details fro"...
0x5da5e  ldloc.s  7
0x5da60  ldstr    aChannelMigrati_0// "Channel Migration Open Details Error"
0x5da65  ldc.i4.1
0x5da66  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetryOperation::RecordException(string, class [mscorlib]System.Exception, string, bool)
0x5da6b  rethrow
0x5da6d  ldloc.1
0x5da6e  brfalse.s loc_5DA76
0x5da70  ldloc.1
0x5da71  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5da76  endfinally
0x5da77  ret
```
