# TimeZoneSyncTask.Data.Rule::ToString

- ea: `0xf590`
- end: `0xf5d0`
- name: `TimeZoneSyncTask.Data.Rule::ToString`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0xf4e0`
- `0xf500`
- `0xf590`

## pseudocode

```c

```

## disassembly

```asm
0xf590  ldarg.0
0xf591  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0xf596  brfalse.s loc_F5B2
0xf598  ldarg.0
0xf599  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0xf59e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf5a3  brtrue.s loc_F5AC
0xf5a5  ldarg.0
0xf5a6  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0xf5ab  ret
0xf5ac  ldstr    asc_1750E// "-"
0xf5b1  ret
0xf5b2  ldarg.0
0xf5b3  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Rule::get_LocalStandardOffset()
0xf5b8  stloc.0
0xf5b9  ldloca.s 0
0xf5bb  ldstr    aC// "c"
0xf5c0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf5c5  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf5ca  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0xf5cf  ret
```
