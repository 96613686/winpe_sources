# TimeZoneSyncTask.Data.RegistryTimeZoneData::IsValid

- ea: `0xfe80`
- end: `0xfeac`
- name: `TimeZoneSyncTask.Data.RegistryTimeZoneData::IsValid`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0xdd20`
- `0xfdf0`

## callees

- `0xce30`
- `0xfa00`

## pseudocode

```c

```

## disassembly

```asm
0xfe80  ldarg.0
0xfe81  ldflda   valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::StandardDate
0xfe86  call     instance bool TimeZoneSyncTask.Data.SYSTEMTIME::IsValid()
0xfe8b  ldstr    aExpectingValid_5// "expecting valid StandardDate"
0xfe90  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfe95  ldarg.0
0xfe96  ldflda   valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightDate
0xfe9b  call     instance bool TimeZoneSyncTask.Data.SYSTEMTIME::IsValid()
0xfea0  ldstr    aExpectingValid_6// "expecting valid DaylightDate"
0xfea5  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xfeaa  ldc.i4.1
0xfeab  ret
```
