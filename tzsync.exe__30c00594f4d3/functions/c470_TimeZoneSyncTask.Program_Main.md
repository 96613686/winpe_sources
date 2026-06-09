# TimeZoneSyncTask.Program::Main

- ea: `0xc470`
- end: `0xc61d`
- name: `TimeZoneSyncTask.Program::Main`
- size: `429`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1200`
- `0xc470`
- `0xc620`
- `0xc690`
- `0xc6d0`
- `0xc6e0`
- `0xced0`
- `0xcee0`
- `0xcff0`
- `0xd1e0`
- `0xd740`
- `0xd8d0`
- `0xd900`
- `0xd930`
- `0xdab0`

## string_xrefs

- `0xc4e5`: `OneSettings Sync Completed {0}, duration:{1:0.000}s`
- `0xc536`: `%windir%\Globalization\Time Zone\timezones.xml`
- `0xc540`: `%windir%\Globalization\Time Zone\timezoneMapping.xml`
- `0xc5d3`: `tzsync Completed {0}, duration:{1:0.000}s`

## pseudocode

```c

```

## disassembly

```asm
0xc470  .entrypoint// "TimeZoneSync.Resources"
0xc475  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0xc47a  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0xc47f  stsfld   class [mscorlib]System.Resources.ResourceManager TimeZoneSyncTask.Program::resourceManager
0xc484  newobj   instance void TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::.ctor()
0xc489  stsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc48e  call     bool TimeZoneSyncTask.Program::IsTzsyncElevated()
0xc493  brfalse  loc_C611
0xc498  ldsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc49d  callvirt instance bool TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncStart()
0xc4a2  pop
0xc4a3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc4a8  stloc.0
0xc4a9  ldc.i4.0
0xc4aa  ldstr    aTzsyncStarted0// "tzsync Started {0}"
0xc4af  ldloc.0
0xc4b0  box      [mscorlib]System.DateTime
0xc4b5  call     string [mscorlib]System.String::Format(string, object)
0xc4ba  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc4bf  ldsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc4c4  callvirt instance bool TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteInitializationStart()
0xc4c9  pop
0xc4ca  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xc4cf  brfalse.s loc_C52A
0xc4d1  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0xc4d6  newobj   instance void TimeZoneSyncTask.TimeZoneOneSettingsSync::.ctor(string pathTimeZoneRoot)
0xc4db  stloc.s  4
0xc4dd  ldloc.s  4
0xc4df  callvirt instance void TimeZoneSyncTask.TimeZoneOneSettingsSync::Sync()
0xc4e4  ldc.i4.0
0xc4e5  ldstr    aOnesettingsSyn// "OneSettings Sync Completed {0}, duratio"...
0xc4ea  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc4ef  box      [mscorlib]System.DateTime
0xc4f4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc4f9  ldloc.0
0xc4fa  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xc4ff  stloc.s  5
0xc501  ldloca.s 5
0xc503  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xc508  box      [mscorlib]System.Double
0xc50d  call     string [mscorlib]System.String::Format(string, object, object)
0xc512  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc517  leave.s  loc_C52A
0xc519  stloc.s  6
0xc51b  ldc.i4.1
0xc51c  ldloc.s  6
0xc51e  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc523  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc528  leave.s  loc_C52A
0xc52a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc52f  stloc.1
0xc530  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc535  stloc.2
0xc536  ldstr    aWindirGlobaliz// "%windir%\\Globalization\\Time Zone\\tim"...
0xc53b  call     string [mscorlib]System.Environment::ExpandEnvironmentVariables(string)
0xc540  ldstr    aWindirGlobaliz_0// "%windir%\\Globalization\\Time Zone\\tim"...
0xc545  call     string [mscorlib]System.Environment::ExpandEnvironmentVariables(string)
0xc54a  stloc.3
0xc54b  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0xc550  stloc.s  7
0xc552  ldloc.3
0xc553  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0xc558  stloc.s  8
0xc55a  ldloc.1
0xc55b  ldloc.2
0xc55c  ldloc.s  7
0xc55e  ldloc.s  8
0xc560  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0xc565  newobj   instance void TimeZoneSyncTask.TimeZoneSync::.ctor(valuetype [mscorlib]System.DateTime dtSync, valuetype [mscorlib]System.DateTime dtSyncUtc, class [mscorlib]System.IO.Stream stmTimeZone, class [mscorlib]System.IO.Stream stmMapping, string pathTimeZoneRoot)
0xc56a  stloc.s  9
0xc56c  ldloc.s  9
0xc56e  callvirt instance void TimeZoneSyncTask.TimeZoneSync::Sync()
0xc573  leave.s  loc_C597
0xc575  stloc.s  0xA
0xc577  ldc.i4.1
0xc578  ldloc.s  0xA
0xc57a  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc57f  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc584  ldsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc589  callvirt instance bool TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncError()
0xc58e  pop
0xc58f  ldc.i4.m1
0xc590  call     void [mscorlib]System.Environment::Exit(int32)
0xc595  leave.s  loc_C597
0xc597  nop
0xc598  ldloc.s  9
0xc59a  callvirt instance bool TimeZoneSyncTask.TimeZoneSync::IsLegacyStoreUpdated()
0xc59f  brfalse.s loc_C5A7
0xc5a1  ldc.i4.1
0xc5a2  call     void TimeZoneSyncTask.Notification::Notify(valuetype Type notificationType)
0xc5a7  leave.s  loc_C5D2
0xc5a9  stloc.s  0xB
0xc5ab  ldc.i4.1
0xc5ac  ldloc.s  0xB
0xc5ae  callvirt instance string [mscorlib]System.Exception::get_Message()
0xc5b3  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc5b8  leave.s  loc_C5D2
0xc5ba  ldloc.s  8
0xc5bc  brfalse.s loc_C5C5
0xc5be  ldloc.s  8
0xc5c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc5c5  endfinally
0xc5c6  ldloc.s  7
0xc5c8  brfalse.s loc_C5D1
0xc5ca  ldloc.s  7
0xc5cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc5d1  endfinally
0xc5d2  ldc.i4.0
0xc5d3  ldstr    aTzsyncComplete// "tzsync Completed {0}, duration:{1:0.000"...
0xc5d8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc5dd  box      [mscorlib]System.DateTime
0xc5e2  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc5e7  ldloc.0
0xc5e8  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xc5ed  stloc.s  5
0xc5ef  ldloca.s 5
0xc5f1  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xc5f6  box      [mscorlib]System.Double
0xc5fb  call     string [mscorlib]System.String::Format(string, object, object)
0xc600  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc605  ldsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc60a  callvirt instance bool TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncStop()
0xc60f  pop
0xc610  ret
0xc611  ldc.i4.0
0xc612  ldstr    aTzsyncIsNotRun// "Tzsync is not running Elevated, Quittin"...
0xc617  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xc61c  ret
```
