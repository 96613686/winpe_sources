# TimeZoneSyncTask.Data.RegistryTimeZoneData::ToWindowsProjection

- ea: `0x10020`
- end: `0x10155`
- name: `TimeZoneSyncTask.Data.RegistryTimeZoneData::ToWindowsProjection`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x11030`
- `0x112f0`

## callees

- `0xe760`
- `0xfcb0`
- `0x10020`
- `0x102f0`
- `0x10310`
- `0x10330`
- `0x10350`

## pseudocode

```c

```

## disassembly

```asm
0x10020  ldloca.s 0
0x10022  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x10028  ldloca.s 1
0x1002a  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x10030  ldarg.0
0x10031  ldfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::Bias
0x10036  neg
0x10037  conv.r8
0x10038  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1003d  stloc.s  4
0x1003f  ldarg.0
0x10040  ldfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightBias
0x10045  neg
0x10046  conv.r8
0x10047  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1004c  stloc.s  5
0x1004e  ldarg.0
0x1004f  ldflda   valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::StandardDate
0x10054  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0x10059  brfalse  loc_10128
0x1005e  ldarg.0
0x1005f  ldflda   valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightDate
0x10064  ldfld    unsigned int16 TimeZoneSyncTask.Data.SYSTEMTIME::wMonth
0x10069  brfalse  loc_10128
0x1006e  ldarg.0
0x1006f  ldflda   valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::StandardDate
0x10074  ldarg.1
0x10075  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.SYSTEMTIME::ToDateTime(int32 year)
0x1007a  stloc.2
0x1007b  ldarg.0
0x1007c  ldflda   valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightDate
0x10081  ldarg.1
0x10082  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.SYSTEMTIME::ToDateTime(int32 year)
0x10087  stloc.3
0x10088  ldloc.2
0x10089  call     bool TimeZoneSyncTask.Utils.Extensions::IsLastMomentOfDay(valuetype [mscorlib]System.DateTime dt)
0x1008e  brfalse.s loc_100A1
0x10090  ldloca.s 2
0x10092  ldc.r8   1.0
0x1009b  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMilliseconds(float64)
0x100a0  stloc.2
0x100a1  ldloc.3
0x100a2  call     bool TimeZoneSyncTask.Utils.Extensions::IsLastMomentOfDay(valuetype [mscorlib]System.DateTime dt)
0x100a7  brfalse.s loc_100BA
0x100a9  ldloca.s 3
0x100ab  ldc.r8   1.0
0x100b4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMilliseconds(float64)
0x100b9  stloc.3
0x100ba  ldloc.3
0x100bb  ldarg.1
0x100bc  ldc.i4.1
0x100bd  ldc.i4.1
0x100be  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x100c3  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x100c8  brfalse.s loc_100E2
0x100ca  ldloca.s 0
0x100cc  ldloc.2
0x100cd  ldloc.s  4
0x100cf  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x100d4  ldloc.s  5
0x100d6  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x100db  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x100e0  br.s     loc_10128
0x100e2  ldloc.2
0x100e3  ldarg.1
0x100e4  ldc.i4.1
0x100e5  ldc.i4.1
0x100e6  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x100eb  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x100f0  brfalse.s loc_10103
0x100f2  ldloca.s 1
0x100f4  ldloc.3
0x100f5  ldloc.s  4
0x100f7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x100fc  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x10101  br.s     loc_10128
0x10103  ldloca.s 0
0x10105  ldloc.2
0x10106  ldloc.s  4
0x10108  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x1010d  ldloc.s  5
0x1010f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x10114  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x10119  ldloca.s 1
0x1011b  ldloc.3
0x1011c  ldloc.s  4
0x1011e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x10123  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x10128  ldloca.s 6
0x1012a  initobj  TimeZoneSyncTask.Data.WindowsProjection
0x10130  ldloca.s 6
0x10132  ldloc.s  4
0x10134  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_TsUtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x10139  ldloca.s 6
0x1013b  ldloc.s  5
0x1013d  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_TsLocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x10142  ldloca.s 6
0x10144  ldloc.0
0x10145  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_StandardDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x1014a  ldloca.s 6
0x1014c  ldloc.1
0x1014d  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_DaylightDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x10152  ldloc.s  6
0x10154  ret
```
