# TimeZoneSyncTask.Core.RegistryOverwrite::UpdateRegCache

- ea: `0x11190`
- end: `0x112ea`
- name: `TimeZoneSyncTask.Core.RegistryOverwrite::UpdateRegCache`
- size: `346`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x11030`
- `0x112f0`
- `0x11550`

## callees

- `0x1050`
- `0xce40`
- `0xcfb0`
- `0xd1a0`
- `0xd1b0`
- `0x11190`

## string_xrefs

- `0x1119d`: `Registry`
- `0x111d3`: `Registry`
- `0x1128c`: `Registry`
- `0x112b3`: `refreshed kernel registry cache for {0}`
- `0x112c9`: `refreshed kernel registry cache for {0}`

## pseudocode

```c

```

## disassembly

```asm
0x11190  ldarg.0
0x11191  ldarg.1
0x11192  ldc.i4.1
0x11193  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x11198  stloc.0
0x11199  ldloc.0
0x1119a  ldnull
0x1119b  cgt.un
0x1119d  ldstr    aRegistry// "Registry"
0x111a2  ldstr    aExpectingNonNu_1// "expecting non-null time zone regkey"
0x111a7  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0x111ac  ldloc.0
0x111ad  ldstr    aTzi// "TZI"
0x111b2  ldarg.2
0x111b3  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object)
0x111b8  ldloca.s 1
0x111ba  initobj  TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION
0x111c0  ldloca.s 1
0x111c2  call     unsigned int32 TimeZoneSyncTask.NativeMethods::GetDynamicTimeZoneInformation([out] valuetype TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION& pDynamicTimeZoneInformation)
0x111c7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x111cc  stloc.2
0x111cd  ldc.i4.0
0x111ce  clt.un
0x111d0  ldc.i4.0
0x111d1  ceq
0x111d3  ldstr    aRegistry// "Registry"
0x111d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x111dd  ldstr    aFailedToGetDyn// "failed to get dynamic tzi: 0x{0:x}"
0x111e2  ldloc.2
0x111e3  box      [mscorlib]System.Int32
0x111e8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x111ed  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0x111f2  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x111f7  brfalse.s loc_11214
0x111f9  ldstr    aCurrentWindows// "current windows tz: {0}"
0x111fe  ldc.i4.1
0x111ff  newarr   [mscorlib]System.Object
0x11204  dup
0x11205  ldc.i4.0
0x11206  ldloc.1
0x11207  ldfld    string TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::TimeZoneKeyName
0x1120c  stelem.ref
0x1120d  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x11212  br.s     loc_1122D
0x11214  ldstr    aCurrentWindows// "current windows tz: {0}"
0x11219  ldc.i4.1
0x1121a  newarr   [mscorlib]System.Object
0x1121f  dup
0x11220  ldc.i4.0
0x11221  ldloc.1
0x11222  ldfld    string TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::TimeZoneKeyName
0x11227  stelem.ref
0x11228  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x1122d  ldloc.1
0x1122e  ldfld    string TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::TimeZoneKeyName
0x11233  ldarg.1
0x11234  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11239  brfalse  loc_112DD
0x1123e  ldloca.s 1
0x11240  ldarg.3
0x11241  ldfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::Bias
0x11246  stfld    int32 TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::Bias
0x1124b  ldloca.s 1
0x1124d  ldarg.3
0x1124e  ldfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::StandardBias
0x11253  stfld    int32 TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::StandardBias
0x11258  ldloca.s 1
0x1125a  ldarg.3
0x1125b  ldfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightBias
0x11260  stfld    int32 TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::DaylightBias
0x11265  ldloca.s 1
0x11267  ldarg.3
0x11268  ldfld    valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::StandardDate
0x1126d  stfld    valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::StandardDate
0x11272  ldloca.s 1
0x11274  ldarg.3
0x11275  ldfld    valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightDate
0x1127a  stfld    valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION::DaylightDate
0x1127f  ldloca.s 1
0x11281  call     bool TimeZoneSyncTask.NativeMethods::SetDynamicTimeZOneInformation([hasfieldmarshal] valuetype TimeZoneSyncTask.Data.DYNAMIC_TIME_ZONE_INFORMATION&)
0x11286  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1128b  stloc.3
0x1128c  ldstr    aRegistry// "Registry"
0x11291  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11296  ldstr    aFailedToSetDyn// "failed to set dynamic tzi for {0}: 0x{1"...
0x1129b  ldarg.1
0x1129c  ldloc.3
0x1129d  box      [mscorlib]System.Int32
0x112a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x112a7  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0x112ac  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x112b1  brfalse.s loc_112C9
0x112b3  ldstr    aRefreshedKerne// "refreshed kernel registry cache for {0}"
0x112b8  ldc.i4.1
0x112b9  newarr   [mscorlib]System.Object
0x112be  dup
0x112bf  ldc.i4.0
0x112c0  ldarg.1
0x112c1  stelem.ref
0x112c2  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0x112c7  leave.s  loc_112E9
0x112c9  ldstr    aRefreshedKerne// "refreshed kernel registry cache for {0}"
0x112ce  ldc.i4.1
0x112cf  newarr   [mscorlib]System.Object
0x112d4  dup
0x112d5  ldc.i4.0
0x112d6  ldarg.1
0x112d7  stelem.ref
0x112d8  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0x112dd  leave.s  loc_112E9
0x112df  ldloc.0
0x112e0  brfalse.s loc_112E8
0x112e2  ldloc.0
0x112e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x112e8  endfinally
0x112e9  ret
```
