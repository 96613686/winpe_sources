# Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::GetBulletinsCarousel

- ea: `0x2aa30`
- end: `0x2abaf`
- name: `Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::GetBulletinsCarousel`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x2aa30`
- `0x2ac00`
- `0x2b4d0`
- `0x2b530`
- `0x2b800`
- `0x2b810`
- `0x2b820`
- `0x2b830`
- `0x3a8b0`

## string_xrefs

- `0x2ab2a`: `Task to retrieve bulletin targeted notifications did not complete in time.`

## pseudocode

```c

```

## disassembly

```asm
0x2aa30  ldarg.0
0x2aa31  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>>> Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::bulletinsCarouselTargetedNotificationsTask
0x2aa36  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::get_IsCanceled()
0x2aa3b  brtrue   loc_2AB57
0x2aa40  ldarg.0
0x2aa41  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::cancellationTokenSource
0x2aa46  callvirt instance bool [mscorlib]System.Threading.CancellationTokenSource::get_IsCancellationRequested()
0x2aa4b  brtrue   loc_2AB57
0x2aa50  ldarg.0
0x2aa51  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>>> Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::bulletinsCarouselTargetedNotificationsTask
0x2aa56  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::get_IsCompleted()
0x2aa5b  brfalse  loc_2AB0E
0x2aa60  ldarg.0
0x2aa61  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>>> Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::bulletinsCarouselTargetedNotificationsTask
0x2aa66  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>>>::get_Result()
0x2aa6b  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>, bool> <>c::<>9__5_0
0x2aa70  dup
0x2aa71  brtrue.s loc_2AA8A
0x2aa73  pop
0x2aa74  ldsfld   class <>c <>c::<>9
0x2aa79  ldftn    instance bool <>c::<GetBulletinsCarousel>b__5_0(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel> action)
0x2aa7f  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>, bool>::.ctor(object, native int)
0x2aa84  dup
0x2aa85  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>, bool> <>c::<>9__5_0
0x2aa8a  call     T0x2B0001AA
0x2aa8f  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>, int32> <>c::<>9__5_1
0x2aa94  dup
0x2aa95  brtrue.s loc_2AAAE
0x2aa97  pop
0x2aa98  ldsfld   class <>c <>c::<>9
0x2aa9d  ldftn    instance int32 <>c::<GetBulletinsCarousel>b__5_1(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel> c)
0x2aaa3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>, int32>::.ctor(object, native int)
0x2aaa8  dup
0x2aaa9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>, int32> <>c::<>9__5_1
0x2aaae  call     T0x2B0001AB
0x2aab3  ldarg.0
0x2aab4  ldftn    instance class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::CreateBulletinsCarouselFromTargetedNotification(class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel> action)
0x2aaba  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.TargetedNotifications.TargetedNotificationsAction`1<class Microsoft.VisualStudio.Setup.Installer.TargetedNotifications.BulletinsCarousel>, class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel>::.ctor(object, native int)
0x2aabf  call     T0x2B0001AC
0x2aac4  dup
0x2aac5  brtrue.s loc_2AACF
0x2aac7  pop
0x2aac8  call     T0x2B0001AD
0x2aacd  stloc.3
0x2aace  ldloc.3
0x2aacf  stloc.0
0x2aad0  ldarg.0
0x2aad1  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2aad6  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.IBulletinsCarouselFilter Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_BulletinsCarouselFilter()
0x2aadb  ldarg.1
0x2aadc  ldloc.0
0x2aadd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel> Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.IBulletinsCarouselFilter::Filter(class Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstallingProductModel product, class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel> carousels)
0x2aae2  call     T0x2B0001AE
0x2aae7  stloc.1
0x2aae8  ldarg.0
0x2aae9  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2aaee  callvirt instance class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.IBulletinSettingsRepository Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_BulletinSettingsRepository()
0x2aaf3  ldarg.1
0x2aaf4  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Models.Products.IInstalledProductIdentityModel::get_InstanceId()
0x2aaf9  callvirt instance string Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.IBulletinSettingsRepository::GetLastShownCarouselId(string instanceId)
0x2aafe  stloc.2
0x2aaff  ldarg.0
0x2ab00  ldloc.1
0x2ab01  ldloc.2
0x2ab02  call     class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::GetCarousel(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel>, string carousels)
0x2ab07  stfld    class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::bulletinsCarousel
0x2ab0c  br.s     loc_2AB57
0x2ab0e  ldarg.0
0x2ab0f  ldfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::cancellationTokenSource
0x2ab14  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0x2ab19  ldarg.0
0x2ab1a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2ab1f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_Logger()
0x2ab24  dup
0x2ab25  brtrue.s loc_2AB2A
0x2ab27  pop
0x2ab28  br.s     loc_2AB39
0x2ab2a  ldstr    aTaskToRetrieve// "Task to retrieve bulletin targeted noti"...
0x2ab2f  call     T0x2B000010
0x2ab34  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteWarning(string, object[])
0x2ab39  ldarg.0
0x2ab3a  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2ab3f  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_Telemetry()
0x2ab44  dup
0x2ab45  brtrue.s loc_2AB4A
0x2ab47  pop
0x2ab48  br.s     loc_2AB57
0x2ab4a  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::GetBulletinActionsTimeoutEvent
0x2ab4f  ldnull
0x2ab50  ldnull
0x2ab51  ldc.i4.0
0x2ab52  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteEvent(string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, object, bool)
0x2ab57  leave.s  loc_2ABA8
0x2ab59  stloc.s  4
0x2ab5b  ldarg.0
0x2ab5c  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2ab61  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_Logger()
0x2ab66  dup
0x2ab67  brtrue.s loc_2AB6C
0x2ab69  pop
0x2ab6a  br.s     loc_2AB7D
0x2ab6c  ldloc.s  4
0x2ab6e  ldstr    aFailedToGetBul// "Failed to get bulletin targeted notific"...
0x2ab73  call     T0x2B000010
0x2ab78  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteError(class [mscorlib]System.Exception, string, object[])
0x2ab7d  ldarg.0
0x2ab7e  ldfld    class Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::serviceOptions
0x2ab83  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry Microsoft.VisualStudio.Setup.Installer.ServiceOptions.BulletinServiceOptions::get_Telemetry()
0x2ab88  dup
0x2ab89  brtrue.s loc_2AB8E
0x2ab8b  pop
0x2ab8c  br.s     loc_2ABA6
0x2ab8e  ldsfld   string Microsoft.VisualStudio.Setup.Installer.CommonInstallerTelemetryConstants::GetBulletinActionsFaultEvent
0x2ab93  ldstr    aFailedToGetBul_0// "Failed to get bulletin targeted notific"...
0x2ab98  ldnull
0x2ab99  ldloc.s  4
0x2ab9b  ldnull
0x2ab9c  ldc.i4.0
0x2ab9d  ldnull
0x2ab9e  ldc.i4.0
0x2ab9f  ldnull
0x2aba0  ldc.i4.0
0x2aba1  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ITelemetry::WriteFault(string, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>, class [mscorlib]System.Exception, object, bool, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.BucketParameters, bool, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>, bool)
0x2aba6  leave.s  loc_2ABA8
0x2aba8  ldarg.0
0x2aba9  ldfld    class Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinsCarousel Microsoft.VisualStudio.Setup.Installer.Services.Bulletins.BulletinService::bulletinsCarousel
0x2abae  ret
```
