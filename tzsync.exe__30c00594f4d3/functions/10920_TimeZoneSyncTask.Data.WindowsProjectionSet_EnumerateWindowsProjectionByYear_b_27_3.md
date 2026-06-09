# TimeZoneSyncTask.Data.WindowsProjectionSet::<EnumerateWindowsProjectionByYear>b__27_3

- ea: `0x10920`
- end: `0x10959`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::<EnumerateWindowsProjectionByYear>b__27_3`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x102f0`
- `0x10310`
- `0x10330`
- `0x10350`
- `0x10550`

## pseudocode

```c

```

## disassembly

```asm
0x10920  ldloca.s 0
0x10922  initobj  TimeZoneSyncTask.Data.WindowsProjection
0x10928  ldloca.s 0
0x1092a  ldarg.1
0x1092b  callvirt instance var<u1> class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_tsUtcOffset()
0x10930  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_TsUtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x10935  ldloca.s 0
0x10937  ldarg.0
0x10938  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjectionSet::get_TsLocalStandardOffset()
0x1093d  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_TsLocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x10942  ldloca.s 0
0x10944  ldarg.1
0x10945  callvirt instance var<u1> class <>f__AnonymousType5`2<valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_dtStandardDate()
0x1094a  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_StandardDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x1094f  ldloca.s 0
0x10951  ldarg.2
0x10952  call     instance void TimeZoneSyncTask.Data.WindowsProjection::set_DaylightDate(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x10957  ldloc.0
0x10958  ret
```
