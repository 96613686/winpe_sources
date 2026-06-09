# TimeZoneSyncTask.Data.DstTransitionRule::Equals_0

- ea: `0xf130`
- end: `0xf1cd`
- name: `TimeZoneSyncTask.Data.DstTransitionRule::Equals_0`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0xf110`

## callees

- `0xf030`
- `0xf050`
- `0xf070`
- `0xf090`
- `0xf0b0`
- `0xf0d0`
- `0xf0f0`
- `0xf130`

## pseudocode

```c

```

## disassembly

```asm
0xf130  ldarg.0
0xf131  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_From()
0xf136  ldarga.s 1
0xf138  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_From()
0xf13d  bne.un   loc_F1CB
0xf142  ldarg.0
0xf143  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_To()
0xf148  ldarga.s 1
0xf14a  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_To()
0xf14f  bne.un.s loc_F1CB
0xf151  ldarg.0
0xf152  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_In()
0xf157  ldarga.s 1
0xf159  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_In()
0xf15e  bne.un.s loc_F1CB
0xf160  ldarg.0
0xf161  call     instance valuetype TimeZoneSyncTask.Data.DayOfMonth TimeZoneSyncTask.Data.DstTransitionRule::get_On()
0xf166  stloc.0
0xf167  ldloca.s 0
0xf169  ldarga.s 1
0xf16b  call     instance valuetype TimeZoneSyncTask.Data.DayOfMonth TimeZoneSyncTask.Data.DstTransitionRule::get_On()
0xf170  box      TimeZoneSyncTask.Data.DayOfMonth
0xf175  constrained. TimeZoneSyncTask.Data.DayOfMonth
0xf17b  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xf180  brfalse.s loc_F1CB
0xf182  ldarg.0
0xf183  call     instance valuetype TimeZoneSyncTask.Data.TimeOfDay TimeZoneSyncTask.Data.DstTransitionRule::get_At()
0xf188  stloc.1
0xf189  ldloca.s 1
0xf18b  ldarga.s 1
0xf18d  call     instance valuetype TimeZoneSyncTask.Data.TimeOfDay TimeZoneSyncTask.Data.DstTransitionRule::get_At()
0xf192  box      TimeZoneSyncTask.Data.TimeOfDay
0xf197  constrained. TimeZoneSyncTask.Data.TimeOfDay
0xf19d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0xf1a2  brfalse.s loc_F1CB
0xf1a4  ldarg.0
0xf1a5  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.DstTransitionRule::get_Save()
0xf1aa  ldarga.s 1
0xf1ac  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.DstTransitionRule::get_Save()
0xf1b1  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xf1b6  brfalse.s loc_F1CB
0xf1b8  ldarg.0
0xf1b9  call     instance string TimeZoneSyncTask.Data.DstTransitionRule::get_Letter()
0xf1be  ldarga.s 1
0xf1c0  call     instance string TimeZoneSyncTask.Data.DstTransitionRule::get_Letter()
0xf1c5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf1ca  ret
0xf1cb  ldc.i4.0
0xf1cc  ret
```
