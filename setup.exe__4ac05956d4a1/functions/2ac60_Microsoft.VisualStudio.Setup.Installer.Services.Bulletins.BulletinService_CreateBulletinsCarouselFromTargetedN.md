# Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::CreateBulletinsCarouselFromTargetedNotification

- ea: `0x2ac60`
- end: `0x2ad75`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::CreateBulletinsCarouselFromTargetedNotification`
- size: `277`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1a850`
- `0x1a960`
- `0x1a970`
- `0x1a980`
- `0x1a990`
- `0x2a800`
- `0x2abb0`
- `0x2ac60`
- `0x2b800`
- `0x2b810`

## string_xrefs

- `0x2ad0e`: `Invalid bulletin found during deserialization`

## pseudocode

```c

```

## disassembly

```asm
0x2ac60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.Bulletin>::.ctor()
0x2ac65  stloc.0
0x2ac66  ldarg.1
0x2ac67  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>::get_Action()
0x2ac6c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin> Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel::get_Bulletins()
0x2ac71  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin>::GetEnumerator()
0x2ac76  stloc.1
0x2ac77  br       loc_2AD2A
0x2ac7c  ldloc.1
0x2ac7d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin>::get_Current()
0x2ac82  stloc.2
0x2ac83  ldloc.2
0x2ac84  ldloca.s 3
0x2ac86  call     bool Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::TryCreateBulletinFromTargetedNotification(class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin tnBulletin, [out] class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.Bulletin& bulletin)
0x2ac8b  brtrue   loc_2AD23
0x2ac90  ldarg.0
0x2ac91  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2ac96  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_Logger()
0x2ac9b  dup
0x2ac9c  brtrue.s loc_2ACA1
0x2ac9e  pop
0x2ac9f  br.s     loc_2ACC0
0x2aca1  ldstr    aFailedToConver// "Failed to convert bulletin with id "
0x2aca6  ldloc.2
0x2aca7  callvirt instance string Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::get_Id()
0x2acac  ldstr    aToAValidBullet// " to a valid bulletin. Skipping that bul"...
0x2acb1  call     string [mscorlib]System.String::Concat(string, string, string)
0x2acb6  call     T0x2B000010
0x2acbb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2acc0  ldarg.0
0x2acc1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2acc6  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_Telemetry()
0x2accb  brfalse.s loc_2AD2A
0x2accd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x2acd2  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinRuleIdProperty
0x2acd7  stloc.s  5
0x2acd9  dup
0x2acda  ldloc.s  5
0x2acdc  ldarg.1
0x2acdd  callvirt instance string class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>::get_RuleId()
0x2ace2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2ace7  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::BulletinIdProperty
0x2acec  stloc.s  6
0x2acee  dup
0x2acef  ldloc.s  6
0x2acf1  ldloc.2
0x2acf2  callvirt instance string Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.Bulletin::get_Id()
0x2acf7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2acfc  stloc.s  4
0x2acfe  ldarg.0
0x2acff  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2ad04  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_Telemetry()
0x2ad09  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::ConvertBulletinErrorEvent
0x2ad0e  ldstr    aInvalidBulleti// "Invalid bulletin found during deseriali"...
0x2ad13  ldloc.s  4
0x2ad15  ldnull
0x2ad16  ldnull
0x2ad17  ldc.i4.0
0x2ad18  ldnull
0x2ad19  ldc.i4.0
0x2ad1a  ldnull
0x2ad1b  ldc.i4.0
0x2ad1c  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x2ad21  br.s     loc_2AD2A
0x2ad23  ldloc.0
0x2ad24  ldloc.3
0x2ad25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.Bulletin>::Add(var<u1>)
0x2ad2a  ldloc.1
0x2ad2b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2ad30  brtrue   loc_2AC7C
0x2ad35  leave.s  loc_2AD41
0x2ad37  ldloc.1
0x2ad38  brfalse.s loc_2AD40
0x2ad3a  ldloc.1
0x2ad3b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ad40  endfinally
0x2ad41  ldarg.1
0x2ad42  callvirt instance string class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>::get_RuleId()
0x2ad47  ldloc.0
0x2ad48  ldarg.1
0x2ad49  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>::get_Action()
0x2ad4e  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel::get_VersionRange()
0x2ad53  ldarg.1
0x2ad54  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>::get_Action()
0x2ad59  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel::get_WorkloadIds()
0x2ad5e  ldarg.1
0x2ad5f  callvirt instance var<u1> class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>::get_Action()
0x2ad64  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel::get_ChannelIds()
0x2ad69  ldarg.1
0x2ad6a  callvirt instance valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.RemoteSettings.ActionPolicies class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>::get_Policies()
0x2ad6f  newobj   instance void Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel::.ctor(string id, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.Bulletin> bulletins, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.VersionRange versionRange, class [System]System.Collections.Generic.ISet`1<string> workloadIds, class [System]System.Collections.Generic.ISet`1<string> channelIds, valuetype [Microsoft.VisualStudio.Telemetry]Microsoft.VisualStudio.RemoteSettings.ActionPolicies policies)
0x2ad74  ret
```
