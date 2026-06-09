# TimeZoneSyncTask.Data.RegistryTimeZoneData::FromWindowsProjection

- ea: `0xfeb0`
- end: `0x10019`
- name: `TimeZoneSyncTask.Data.RegistryTimeZoneData::FromWindowsProjection`
- size: `361`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x11030`
- `0x112f0`
- `0x11550`

## callees

- `0xf940`
- `0xfeb0`
- `0x102e0`
- `0x10300`
- `0x10320`
- `0x10340`

## pseudocode

```c

```

## disassembly

```asm
0xfeb0  ldarga.s 0
0xfeb2  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0xfeb7  stloc.2
0xfeb8  ldloca.s 2
0xfeba  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xfebf  brfalse.s loc_FF25
0xfec1  ldarga.s 0
0xfec3  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0xfec8  stloc.2
0xfec9  ldloca.s 2
0xfecb  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xfed0  brfalse.s loc_FF25
0xfed2  ldarga.s 0
0xfed4  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0xfed9  stloc.2
0xfeda  ldloca.s 2
0xfedc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xfee1  ldarga.s 0
0xfee3  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0xfee8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xfeed  ldarga.s 0
0xfeef  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0xfef4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xfef9  call     valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime(valuetype [mscorlib]System.DateTime dt)
0xfefe  stloc.0
0xfeff  ldarga.s 0
0xff01  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0xff06  stloc.2
0xff07  ldloca.s 2
0xff09  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xff0e  ldarga.s 0
0xff10  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0xff15  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xff1a  call     valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime(valuetype [mscorlib]System.DateTime dt)
0xff1f  stloc.1
0xff20  br       loc_FFC5
0xff25  ldarga.s 0
0xff27  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0xff2c  stloc.2
0xff2d  ldloca.s 2
0xff2f  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xff34  brfalse.s loc_FF73
0xff36  ldarg.1
0xff37  ldc.i4.1
0xff38  ldc.i4.1
0xff39  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0xff3e  call     valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime(valuetype [mscorlib]System.DateTime dt)
0xff43  stloc.1
0xff44  ldarga.s 0
0xff46  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0xff4b  stloc.2
0xff4c  ldloca.s 2
0xff4e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xff53  ldarga.s 0
0xff55  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0xff5a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xff5f  ldarga.s 0
0xff61  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0xff66  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xff6b  call     valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime(valuetype [mscorlib]System.DateTime dt)
0xff70  stloc.0
0xff71  br.s     loc_FFC5
0xff73  ldarga.s 0
0xff75  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0xff7a  stloc.2
0xff7b  ldloca.s 2
0xff7d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xff82  brfalse.s loc_FFB5
0xff84  ldarg.1
0xff85  ldc.i4.1
0xff86  ldc.i4.1
0xff87  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0xff8c  call     valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime(valuetype [mscorlib]System.DateTime dt)
0xff91  stloc.0
0xff92  ldarga.s 0
0xff94  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0xff99  stloc.2
0xff9a  ldloca.s 2
0xff9c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0xffa1  ldarga.s 0
0xffa3  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0xffa8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xffad  call     valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.SYSTEMTIME::FromDateTime(valuetype [mscorlib]System.DateTime dt)
0xffb2  stloc.1
0xffb3  br.s     loc_FFC5
0xffb5  ldloca.s 0
0xffb7  initobj  TimeZoneSyncTask.Data.SYSTEMTIME
0xffbd  ldloca.s 1
0xffbf  initobj  TimeZoneSyncTask.Data.SYSTEMTIME
0xffc5  ldloca.s 3
0xffc7  initobj  TimeZoneSyncTask.Data.RegistryTimeZoneData
0xffcd  ldloca.s 3
0xffcf  ldarga.s 0
0xffd1  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0xffd6  stloc.s  4
0xffd8  ldloca.s 4
0xffda  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0xffdf  conv.i4
0xffe0  neg
0xffe1  stfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::Bias
0xffe6  ldloca.s 3
0xffe8  ldc.i4.0
0xffe9  stfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::StandardBias
0xffee  ldloca.s 3
0xfff0  ldarga.s 0
0xfff2  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0xfff7  stloc.s  4
0xfff9  ldloca.s 4
0xfffb  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x10000  conv.i4
0x10001  neg
0x10002  stfld    int32 TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightBias
0x10007  ldloca.s 3
0x10009  ldloc.0
0x1000a  stfld    valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::StandardDate
0x1000f  ldloca.s 3
0x10011  ldloc.1
0x10012  stfld    valuetype TimeZoneSyncTask.Data.SYSTEMTIME TimeZoneSyncTask.Data.RegistryTimeZoneData::DaylightDate
0x10017  ldloc.3
0x10018  ret
```
