# TimeZoneSyncTask.Data.DayOfMonth::FromString

- ea: `0xef60`
- end: `0xf00f`
- name: `TimeZoneSyncTask.Data.DayOfMonth::FromString`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x12530`

## callees

- `0xe8d0`
- `0xec20`
- `0xec40`
- `0xee30`
- `0xee50`
- `0xee70`
- `0xef60`

## pseudocode

```c

```

## disassembly

```asm
0xef60  ldarg.0
0xef61  ldstr    aLast// "last"
0xef66  ldc.i4.4
0xef67  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xef6c  brfalse.s loc_EF9C
0xef6e  ldloca.s 1
0xef70  initobj  TimeZoneSyncTask.Data.DayOfMonth
0xef76  ldloca.s 1
0xef78  ldc.i4.2
0xef79  call     instance void TimeZoneSyncTask.Data.DayOfMonth::set_Type(valuetype TimeZoneSyncTask.Data.DayType value)
0xef7e  ldloca.s 1
0xef80  ldarg.0
0xef81  ldstr    aLast// "last"
0xef86  call     instance int32 [mscorlib]System.String::get_Length()
0xef8b  callvirt instance string [mscorlib]System.String::Substring(int32)
0xef90  call     int32 TimeZoneSyncTask.Utils.Helper::GetDayOfWeekFromAbbreviation(string abbreviation)
0xef95  call     instance void TimeZoneSyncTask.Data.DayOfMonth::set_DayOfWeek(int32 value)
0xef9a  ldloc.1
0xef9b  ret
0xef9c  ldarg.0
0xef9d  ldloca.s 0
0xef9f  call     bool TimeZoneSyncTask.Utils.Helper::TryParseInt32(string s, [out] int32& out)
0xefa4  brfalse.s loc_EFC0
0xefa6  ldloca.s 1
0xefa8  initobj  TimeZoneSyncTask.Data.DayOfMonth
0xefae  ldloca.s 1
0xefb0  ldc.i4.0
0xefb1  call     instance void TimeZoneSyncTask.Data.DayOfMonth::set_Type(valuetype TimeZoneSyncTask.Data.DayType value)
0xefb6  ldloca.s 1
0xefb8  ldloc.0
0xefb9  call     instance void TimeZoneSyncTask.Data.DayOfMonth::set_Day(int32 value)
0xefbe  ldloc.1
0xefbf  ret
0xefc0  ldarg.0
0xefc1  ldc.i4.0
0xefc2  ldstr    aSun// "Sun"
0xefc7  call     instance int32 [mscorlib]System.String::get_Length()
0xefcc  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xefd1  stloc.2
0xefd2  ldarg.0
0xefd3  ldstr    aSun_0// "Sun>="
0xefd8  call     instance int32 [mscorlib]System.String::get_Length()
0xefdd  callvirt instance string [mscorlib]System.String::Substring(int32)
0xefe2  stloc.3
0xefe3  ldloca.s 1
0xefe5  initobj  TimeZoneSyncTask.Data.DayOfMonth
0xefeb  ldloca.s 1
0xefed  ldc.i4.1
0xefee  call     instance void TimeZoneSyncTask.Data.DayOfMonth::set_Type(valuetype TimeZoneSyncTask.Data.DayType value)
0xeff3  ldloca.s 1
0xeff5  ldloc.2
0xeff6  call     int32 TimeZoneSyncTask.Utils.Helper::GetDayOfWeekFromAbbreviation(string abbreviation)
0xeffb  call     instance void TimeZoneSyncTask.Data.DayOfMonth::set_DayOfWeek(int32 value)
0xf000  ldloca.s 1
0xf002  ldloc.3
0xf003  call     int32 TimeZoneSyncTask.Utils.Helper::ParseInt32(string s)
0xf008  call     instance void TimeZoneSyncTask.Data.DayOfMonth::set_Day(int32 value)
0xf00d  ldloc.1
0xf00e  ret
```
