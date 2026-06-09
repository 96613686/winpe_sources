# TimeZoneSyncTask.Data.WindowsProjectionSet::Equals_0

- ea: `0x105b0`
- end: `0x105fd`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::Equals_0`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x10590`

## callees

- `0x104d0`
- `0x10510`
- `0x10530`
- `0x10550`
- `0x105b0`

## pseudocode

```c

```

## disassembly

```asm
0x105b0  ldarg.0
0x105b1  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x105b6  ldarg.1
0x105b7  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x105bc  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::SetEquals(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x105c1  brfalse.s loc_105FB
0x105c3  ldarg.0
0x105c4  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x105c9  ldarg.1
0x105ca  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x105cf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::SetEquals(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x105d4  brfalse.s loc_105FB
0x105d6  ldarg.0
0x105d7  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x105dc  ldarg.1
0x105dd  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x105e2  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::SetEquals(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x105e7  brfalse.s loc_105FB
0x105e9  ldarg.0
0x105ea  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjectionSet::get_TsLocalStandardOffset()
0x105ef  ldarg.1
0x105f0  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjectionSet::get_TsLocalStandardOffset()
0x105f5  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x105fa  ret
0x105fb  ldc.i4.0
0x105fc  ret
```
