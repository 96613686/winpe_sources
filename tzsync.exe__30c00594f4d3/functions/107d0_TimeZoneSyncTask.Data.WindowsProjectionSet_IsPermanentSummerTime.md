# TimeZoneSyncTask.Data.WindowsProjectionSet::IsPermanentSummerTime

- ea: `0x107d0`
- end: `0x108bd`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::IsPermanentSummerTime`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x10700`

## callees

- `0x104d0`
- `0x104f0`
- `0x10510`
- `0x10530`
- `0x10550`
- `0x107d0`

## pseudocode

```c

```

## disassembly

```asm
0x107d0  ldarg.0
0x107d1  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x107d6  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::get_Count()
0x107db  ldc.i4.2
0x107dc  beq.s    loc_107E0
0x107de  ldc.i4.0
0x107df  ret
0x107e0  ldarg.0
0x107e1  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x107e6  call     T0x2B000027
0x107eb  ldarg.0
0x107ec  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x107f1  call     T0x2B000028
0x107f6  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x107fb  stloc.0
0x107fc  ldloca.s 0
0x107fe  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Duration()
0x10803  ldarg.0
0x10804  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjectionSet::get_TsLocalStandardOffset()
0x10809  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1080e  brfalse.s loc_1085E
0x10810  ldarg.0
0x10811  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x10816  call     T0x2B000029
0x1081b  stloc.1
0x1081c  ldarg.0
0x1081d  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_ChangeUtcOffsetsDates()
0x10822  call     T0x2B000029
0x10827  stloc.2
0x10828  ldloca.s 1
0x1082a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1082f  ldloca.s 2
0x10831  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x10836  beq.s    loc_1083B
0x10838  ldc.i4.0
0x10839  br.s     loc_1085A
0x1083b  ldloca.s 1
0x1083d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x10842  brtrue.s loc_10847
0x10844  ldc.i4.1
0x10845  br.s     loc_1085A
0x10847  ldloca.s 1
0x10849  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x1084e  ldloca.s 2
0x10850  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::GetValueOrDefault()
0x10855  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1085a  brfalse.s loc_1085E
0x1085c  ldc.i4.1
0x1085d  ret
0x1085e  ldarg.0
0x1085f  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x10864  ldloca.s 2
0x10866  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1086c  ldloc.2
0x1086d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Contains(var<u1>)
0x10872  brfalse.s loc_108BB
0x10874  ldarg.0
0x10875  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x1087a  ldloca.s 2
0x1087c  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x10882  ldloc.2
0x10883  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Contains(var<u1>)
0x10888  brfalse.s loc_108BB
0x1088a  ldarg.0
0x1088b  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x10890  call     T0x2B000027
0x10895  ldarg.0
0x10896  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x1089b  call     T0x2B000028
0x108a0  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Subtraction(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x108a5  stloc.0
0x108a6  ldloca.s 0
0x108a8  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Duration()
0x108ad  ldsfld   valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjectionSet::tsArbitraryCutoff
0x108b2  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x108b7  brfalse.s loc_108BB
0x108b9  ldc.i4.1
0x108ba  ret
0x108bb  ldc.i4.0
0x108bc  ret
```
