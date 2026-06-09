# TimeZoneSyncTask.Data.WindowsProjection::Equals_0

- ea: `0x10380`
- end: `0x103ed`
- name: `TimeZoneSyncTask.Data.WindowsProjection::Equals_0`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x10360`

## callees

- `0x102e0`
- `0x10300`
- `0x10320`
- `0x10340`
- `0x10380`

## pseudocode

```c

```

## disassembly

```asm
0x10380  ldarg.0
0x10381  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0x10386  ldarga.s 1
0x10388  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0x1038d  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x10392  brfalse.s loc_103EB
0x10394  ldarg.0
0x10395  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0x1039a  ldarga.s 1
0x1039c  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0x103a1  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x103a6  brfalse.s loc_103EB
0x103a8  ldarg.0
0x103a9  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x103ae  stloc.0
0x103af  ldloca.s 0
0x103b1  ldarga.s 1
0x103b3  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x103b8  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x103bd  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x103c3  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x103c8  brfalse.s loc_103EB
0x103ca  ldarg.0
0x103cb  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x103d0  stloc.0
0x103d1  ldloca.s 0
0x103d3  ldarga.s 1
0x103d5  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x103da  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x103df  constrained. valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x103e5  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x103ea  ret
0x103eb  ldc.i4.0
0x103ec  ret
```
