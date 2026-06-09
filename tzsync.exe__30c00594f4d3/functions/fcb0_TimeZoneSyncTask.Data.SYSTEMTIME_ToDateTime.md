# TimeZoneSyncTask.Data.SYSTEMTIME::ToDateTime

- ea: `0xfcb0`
- end: `0xfd86`
- name: `TimeZoneSyncTask.Data.SYSTEMTIME::ToDateTime`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10020`

## callees

- `0xf910`
- `0xfcb0`

## pseudocode

```c

```

## disassembly

```asm
0xfcb0  ldarg.0
0xfcb1  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDay
0xfcb6  ldc.i4.5
0xfcb7  bne.un.s loc_FD0F
0xfcb9  ldloca.s 0
0xfcbb  ldarg.1
0xfcbc  ldarg.0
0xfcbd  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0xfcc2  ldarg.1
0xfcc3  ldarg.0
0xfcc4  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0xfcc9  call     int32 [mscorlib]System.DateTime::DaysInMonth(int32, int32)
0xfcce  ldarg.0
0xfccf  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wHour
0xfcd4  ldarg.0
0xfcd5  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMinute
0xfcda  ldarg.0
0xfcdb  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wSecond
0xfce0  ldarg.0
0xfce1  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMilliseconds
0xfce6  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, int32)
0xfceb  br.s     loc_FCFE
0xfced  ldloca.s 0
0xfcef  ldc.r8   -1.0
0xfcf8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xfcfd  stloc.0
0xfcfe  ldloca.s 0
0xfd00  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0xfd05  ldarg.0
0xfd06  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDayOfWeek
0xfd0b  bne.un.s loc_FCED
0xfd0d  br.s     loc_FD6B
0xfd0f  ldloca.s 0
0xfd11  ldarg.1
0xfd12  ldarg.0
0xfd13  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0xfd18  ldc.i4.1
0xfd19  ldarg.0
0xfd1a  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wHour
0xfd1f  ldarg.0
0xfd20  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMinute
0xfd25  ldarg.0
0xfd26  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wSecond
0xfd2b  ldarg.0
0xfd2c  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMilliseconds
0xfd31  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, int32)
0xfd36  br.s     loc_FD49
0xfd38  ldloca.s 0
0xfd3a  ldc.r8   1.0
0xfd43  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xfd48  stloc.0
0xfd49  ldloca.s 0
0xfd4b  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0xfd50  ldarg.0
0xfd51  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDayOfWeek
0xfd56  bne.un.s loc_FD38
0xfd58  ldloca.s 0
0xfd5a  ldc.i4.7
0xfd5b  ldarg.0
0xfd5c  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDay
0xfd61  ldc.i4.1
0xfd62  sub
0xfd63  mul
0xfd64  conv.r8
0xfd65  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xfd6a  stloc.0
0xfd6b  ldarg.0
0xfd6c  call     instance bool TimeZoneSyncTask.Data.SYSTEMTIME::IsLastMomentOfDay()
0xfd71  brtrue.s loc_FD75
0xfd73  ldloc.0
0xfd74  ret
0xfd75  ldloca.s 0
0xfd77  ldc.r8   1.0
0xfd80  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMilliseconds(float64)
0xfd85  ret
```
