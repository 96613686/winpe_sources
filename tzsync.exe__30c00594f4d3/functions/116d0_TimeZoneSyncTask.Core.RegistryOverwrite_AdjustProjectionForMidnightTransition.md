# TimeZoneSyncTask.Core.RegistryOverwrite::AdjustProjectionForMidnightTransition

- ea: `0x116d0`
- end: `0x11770`
- name: `TimeZoneSyncTask.Core.RegistryOverwrite::AdjustProjectionForMidnightTransition`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x11030`
- `0x112f0`
- `0x11550`

## callees

- `0x102e0`
- `0x102f0`
- `0x10300`
- `0x10310`
- `0x10320`
- `0x10330`
- `0x10340`
- `0x10350`
- `0x11660`
- `0x116d0`

## pseudocode

```c

```

## disassembly

```asm
0x116d0  ldarga.s 0
0x116d2  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x116d7  stloc.0
0x116d8  ldarga.s 0
0x116da  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x116df  stloc.1
0x116e0  ldarga.s 0
0x116e2  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x116e7  stloc.2
0x116e8  ldloca.s 2
0x116ea  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x116ef  brfalse.s loc_1170D
0x116f1  ldloca.s 0
0x116f3  ldarga.s 0
0x116f5  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x116fa  stloc.2
0x116fb  ldloca.s 2
0x116fd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x11702  ldarg.1
0x11703  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.RegistryOverwrite::AdjustDateTimeForMidnightTransition(valuetype [mscorlib]System.DateTime dt, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions)
0x11708  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x1170d  ldarga.s 0
0x1170f  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11714  stloc.2
0x11715  ldloca.s 2
0x11717  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1171c  brfalse.s loc_1173A
0x1171e  ldloca.s 1
0x11720  ldarga.s 0
0x11722  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11727  stloc.2
0x11728  ldloca.s 2
0x1172a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x1172f  ldarg.1
0x11730  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.RegistryOverwrite::AdjustDateTimeForMidnightTransition(valuetype [mscorlib]System.DateTime dt, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions)
0x11735  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x1173a  ldloca.s 3
0x1173c  initobj  TimeZoneSyncTask.Data.WindowsProjection
0x11742  ldloca.s 3
0x11744  ldarga.s 0
0x11746  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0x1174b  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_TsUtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x11750  ldloca.s 3
0x11752  ldarga.s 0
0x11754  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0x11759  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_TsLocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x1175e  ldloca.s 3
0x11760  ldloc.0
0x11761  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_StandardDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x11766  ldloca.s 3
0x11768  ldloc.1
0x11769  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_DaylightDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x1176e  ldloc.3
0x1176f  ret
```
