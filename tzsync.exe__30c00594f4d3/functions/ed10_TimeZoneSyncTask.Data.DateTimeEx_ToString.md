# TimeZoneSyncTask.Data.DateTimeEx::ToString

- ea: `0xed10`
- end: `0xed34`
- name: `TimeZoneSyncTask.Data.DateTimeEx::ToString`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0xeaf0`
- `0xec60`
- `0xec80`

## pseudocode

```c

```

## disassembly

```asm
0xed10  ldarg.0
0xed11  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0xed16  stloc.0
0xed17  ldloca.s 0
0xed19  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xed1e  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0xed23  ldarg.0
0xed24  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.DateTimeEx::get_Base()
0xed29  call     string TimeZoneSyncTask.Utils.Helper::FromBaseToString(valuetype TimeZoneSyncTask.Data.TimeBase base)
0xed2e  call     string [mscorlib]System.String::Concat(string, string)
0xed33  ret
```
