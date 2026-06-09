# TimeZoneSyncTask.Data.TimeOfDay::ToString

- ea: `0xf690`
- end: `0xf6be`
- name: `TimeZoneSyncTask.Data.TimeOfDay::ToString`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0xeaf0`
- `0xf5e0`
- `0xf600`

## pseudocode

```c

```

## disassembly

```asm
0xf690  ldarg.0
0xf691  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeOfDay::get_Duration()
0xf696  stloc.0
0xf697  ldloca.s 0
0xf699  ldstr    aC// "c"
0xf69e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf6a3  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf6a8  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0xf6ad  ldarg.0
0xf6ae  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.TimeOfDay::get_Base()
0xf6b3  call     string TimeZoneSyncTask.Utils.Helper::FromBaseToString(valuetype TimeZoneSyncTask.Data.TimeBase base)
0xf6b8  call     string [mscorlib]System.String::Concat(string, string)
0xf6bd  ret
```
