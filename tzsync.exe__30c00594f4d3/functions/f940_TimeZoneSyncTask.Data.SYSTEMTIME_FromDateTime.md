# TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime

- ea: `0xf940`
- end: `0xf9fb`
- name: `TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xfeb0`

## callees

- `0x14370`

## pseudocode

```c

```

## disassembly

```asm
0xf940  newobj   instance void <>c__DisplayClass10_0::.ctor()
0xf945  stloc.0
0xf946  ldloc.0
0xf947  ldarg.0
0xf948  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf94d  ldloca.s 1
0xf94f  initobj  TimeZoneSyncTask.Data.SYSTEMTIME
0xf955  ldloca.s 1
0xf957  ldc.i4.0
0xf958  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wYear
0xf95d  ldloca.s 1
0xf95f  ldloc.0
0xf960  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf965  call     instance int32 [mscorlib]System.DateTime::get_Month()
0xf96a  conv.u2
0xf96b  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0xf970  ldloca.s 1
0xf972  ldloc.0
0xf973  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf978  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0xf97d  conv.u2
0xf97e  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDayOfWeek
0xf983  ldloca.s 1
0xf985  ldc.i4.1
0xf986  ldloc.0
0xf987  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf98c  call     instance int32 [mscorlib]System.DateTime::get_Day()
0xf991  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> [System.Core]System.Linq.Enumerable::Range(int32, int32)
0xf996  ldloc.0
0xf997  ldftn    instance bool <>c__DisplayClass10_0::<FromDateTime>b__0(int32 d)
0xf99d  newobj   instance void class [mscorlib]System.Func`2<int32, bool>::.ctor(object, native int)
0xf9a2  call     T0x2B000020
0xf9a7  conv.u2
0xf9a8  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wDay
0xf9ad  ldloca.s 1
0xf9af  ldloc.0
0xf9b0  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf9b5  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0xf9ba  conv.u2
0xf9bb  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wHour
0xf9c0  ldloca.s 1
0xf9c2  ldloc.0
0xf9c3  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf9c8  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0xf9cd  conv.u2
0xf9ce  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMinute
0xf9d3  ldloca.s 1
0xf9d5  ldloc.0
0xf9d6  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf9db  call     instance int32 [mscorlib]System.DateTime::get_Second()
0xf9e0  conv.u2
0xf9e1  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wSecond
0xf9e6  ldloca.s 1
0xf9e8  ldloc.0
0xf9e9  ldflda   valuetype [mscorlib]System.DateTime <>c__DisplayClass10_0::dt
0xf9ee  call     instance int32 [mscorlib]System.DateTime::get_Millisecond()
0xf9f3  conv.u2
0xf9f4  stfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMilliseconds
0xf9f9  ldloc.1
0xf9fa  ret
```
