# TimeZoneSyncTask.Data.WindowsProjectionSet::ShouldProjectionOccur

- ea: `0x10700`
- end: `0x1076b`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::ShouldProjectionOccur`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0xcea0`

## callees

- `0x104d0`
- `0x10510`
- `0x10530`
- `0x10700`
- `0x107d0`

## pseudocode

```c

```

## disassembly

```asm
0x10700  ldarg.0
0x10701  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x10706  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::get_Count()
0x1070b  ldc.i4.1
0x1070c  ble.s    loc_1073D
0x1070e  ldarg.0
0x1070f  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x10714  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x10719  ldarg.0
0x1071a  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x1071f  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x10724  mul
0x10725  ldc.i4.1
0x10726  bne.un.s loc_1073D
0x10728  ldarg.0
0x10729  call     instance bool TimeZoneSyncTask.Data.WindowsProjectionSet::IsPermanentSummerTime()
0x1072e  brtrue.s loc_1073B
0x10730  ldarga.s 1
0x10732  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10737  ldarg.2
0x10738  cgt
0x1073a  ret
0x1073b  ldc.i4.0
0x1073c  ret
0x1073d  ldarg.0
0x1073e  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x10743  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::get_Count()
0x10748  ldc.i4.1
0x10749  bne.un.s loc_10769
0x1074b  ldarg.0
0x1074c  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x10751  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x10756  ldarg.0
0x10757  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x1075c  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x10761  mul
0x10762  ldc.i4.1
0x10763  clt
0x10765  ldc.i4.0
0x10766  ceq
0x10768  ret
0x10769  ldc.i4.0
0x1076a  ret
```
