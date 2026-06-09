# TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::.ctor

- ea: `0xe120`
- end: `0xe17d`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::.ctor`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0xcee0`

## callees

- `0x1200`
- `0xce40`
- `0xe5e0`

## string_xrefs

- `0xe157`: `Registry`

## pseudocode

```c

```

## disassembly

```asm
0xe120  ldarg.0
0xe121  call     instance void [mscorlib]System.Object::.ctor()
0xe126  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xe12b  call     void [System]System.Diagnostics.Trace::Assert(bool)
0xe130  ldarg.0
0xe131  newobj   instance void TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::.ctor()
0xe136  stfld    class TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::timeZoneDSTSettings
0xe13b  ldarg.0
0xe13c  ldarg.2
0xe13d  stfld    class [Windows]Windows.Data.Json.JsonObject TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::oneSettingsData
0xe142  ldarg.0
0xe143  ldc.i4.0
0xe144  stfld    unsigned int32 TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::systemTzversion
0xe149  ldarg.1
0xe14a  ldstr    aTzversion// "TzVersion"
0xe14f  callvirt instance valuetype [mscorlib]Microsoft.Win32.RegistryValueKind [mscorlib]Microsoft.Win32.RegistryKey::GetValueKind(string)
0xe154  ldc.i4.4
0xe155  ceq
0xe157  ldstr    aRegistry// "Registry"
0xe15c  ldstr    aExpectingDword// "expecting DWORD for TzVersion"
0xe161  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xe166  ldarg.0
0xe167  ldarg.1
0xe168  ldstr    aTzversion// "TzVersion"
0xe16d  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xe172  call     unsigned int32 [mscorlib]System.Convert::ToUInt32(object)
0xe177  stfld    unsigned int32 TimeZoneSyncTask.OneSettings.OneSettingsDSTJsonParser::systemTzversion
0xe17c  ret
```
