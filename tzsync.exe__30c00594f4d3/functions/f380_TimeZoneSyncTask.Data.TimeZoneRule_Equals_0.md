# TimeZoneSyncTask.Data.TimeZoneRule::Equals_0

- ea: `0xf380`
- end: `0xf3ed`
- name: `TimeZoneSyncTask.Data.TimeZoneRule::Equals_0`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0xf360`

## callees

- `0xf2e0`
- `0xf300`
- `0xf320`
- `0xf340`
- `0xf380`

## pseudocode

```c

```

## disassembly

```asm
0xf380  ldarg.0
0xf381  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeZoneRule::get_UtcOffset()
0xf386  ldarga.s 1
0xf388  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeZoneRule::get_UtcOffset()
0xf38d  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xf392  brfalse.s loc_F3EB
0xf394  ldarg.0
0xf395  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0xf39a  stloc.0
0xf39b  ldloca.s 0
0xf39d  ldarga.s 1
0xf39f  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0xf3a4  box      TimeZoneSyncTask.Data.Rule
0xf3a9  constrained. TimeZoneSyncTask.Data.Rule
0xf3af  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xf3b4  brfalse.s loc_F3EB
0xf3b6  ldarg.0
0xf3b7  call     instance string TimeZoneSyncTask.Data.TimeZoneRule::get_Format()
0xf3bc  ldarga.s 1
0xf3be  call     instance string TimeZoneSyncTask.Data.TimeZoneRule::get_Format()
0xf3c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf3c8  brfalse.s loc_F3EB
0xf3ca  ldarg.0
0xf3cb  call     instance valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Data.TimeZoneRule::get_Until()
0xf3d0  stloc.1
0xf3d1  ldloca.s 1
0xf3d3  ldarga.s 1
0xf3d5  call     instance valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Data.TimeZoneRule::get_Until()
0xf3da  box      TimeZoneSyncTask.Data.DateTimeEx
0xf3df  constrained. TimeZoneSyncTask.Data.DateTimeEx
0xf3e5  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xf3ea  ret
0xf3eb  ldc.i4.0
0xf3ec  ret
```
