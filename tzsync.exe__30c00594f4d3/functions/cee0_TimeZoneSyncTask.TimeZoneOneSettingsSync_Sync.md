# TimeZoneSyncTask.TimeZoneOneSettingsSync::Sync

- ea: `0xcee0`
- end: `0xcf50`
- name: `TimeZoneSyncTask.TimeZoneOneSettingsSync::Sync`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0xc470`

## callees

- `0xce40`
- `0xcee0`
- `0xcff0`
- `0xdb40`
- `0xdb50`
- `0xdb70`
- `0xe120`
- `0xe530`
- `0xe6e0`

## string_xrefs

- `0xcf00`: `Registry`
- `0xcef2`: `Syncing OneSettings with Registry`

## pseudocode

```c

```

## disassembly

```asm
0xcee0  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0xcee5  ldarg.0
0xcee6  ldfld    string TimeZoneSyncTask.TimeZoneOneSettingsSync::pathTimeZoneRoot
0xceeb  ldc.i4.1
0xceec  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0xcef1  stloc.0
0xcef2  ldstr    aSyncingOnesett// "Syncing OneSettings with Registry"
0xcef7  call     void [System]System.Diagnostics.Trace::TraceInformation(string)
0xcefc  ldloc.0
0xcefd  ldnull
0xcefe  cgt.un
0xcf00  ldstr    aRegistry// "Registry"
0xcf05  ldstr    aExpectingNonNu// "expecting non-null time zone root regke"...
0xcf0a  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xcf0f  newobj   instance void TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::.ctor()
0xcf14  stloc.1
0xcf15  ldloc.0
0xcf16  ldloc.1
0xcf17  callvirt instance class [Windows]Windows.Data.Json.JsonObject TimeZoneSyncTask.OneSettings.IOneSettingsWrapper::GetOneSettingsPayload()
0xcf1c  newobj   instance void TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::.ctor(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot, class [Windows]Windows.Data.Json.JsonObject oneSettingsData)
0xcf21  dup
0xcf22  callvirt instance void TimeZoneSyncTask.OneSettings.IOneSettingsParser::ParseOneSettingsData()
0xcf27  callvirt instance class TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings TimeZoneSyncTask.OneSettings.IOneSettingsParser::GetTimeZoneDSTSettings()
0xcf2c  ldloc.0
0xcf2d  callvirt instance void TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::SyncDSTDataWithRegistry(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot)
0xcf32  leave.s  loc_CF3E
0xcf34  ldloc.0
0xcf35  brfalse.s loc_CF3D
0xcf37  ldloc.0
0xcf38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcf3d  endfinally
0xcf3e  leave.s  loc_CF4F
0xcf40  stloc.2
0xcf41  ldc.i4.1
0xcf42  ldloc.2
0xcf43  callvirt instance string [mscorlib]System.Exception::get_Message()
0xcf48  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace(valuetype logType type, string log)
0xcf4d  leave.s  loc_CF4F
0xcf4f  ret
```
