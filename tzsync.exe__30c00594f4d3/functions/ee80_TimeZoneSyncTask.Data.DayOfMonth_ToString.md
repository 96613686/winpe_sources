# TimeZoneSyncTask.Data.DayOfMonth::ToString

- ea: `0xee80`
- end: `0xeeea`
- name: `TimeZoneSyncTask.Data.DayOfMonth::ToString`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0xe900`
- `0xee20`
- `0xee40`
- `0xee60`
- `0xee80`

## pseudocode

```c

```

## disassembly

```asm
0xee80  ldarg.0
0xee81  call     instance valuetype TimeZoneSyncTask.Data.DayType TimeZoneSyncTask.Data.DayOfMonth::get_Type()
0xee86  stloc.0
0xee87  ldloc.0
0xee88  brfalse.s loc_EE90
0xee8a  ldloc.0
0xee8b  ldc.i4.1
0xee8c  beq.s    loc_EEA9
0xee8e  br.s     loc_EECF
0xee90  ldarg.0
0xee91  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_Day()
0xee96  stloc.1
0xee97  ldloca.s 1
0xee99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xee9e  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xeea3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xeea8  ret
0xeea9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeeae  ldstr    a01// "{0}>={1}"
0xeeb3  ldarg.0
0xeeb4  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_DayOfWeek()
0xeeb9  call     string TimeZoneSyncTask.Utils.Helper::GetDayOfWeekAbbreviation(int32 dayOfWeek)
0xeebe  ldarg.0
0xeebf  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_Day()
0xeec4  box      [mscorlib]System.Int32
0xeec9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0xeece  ret
0xeecf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeed4  ldstr    aLast0// "last{0}"
0xeed9  ldarg.0
0xeeda  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_DayOfWeek()
0xeedf  call     string TimeZoneSyncTask.Utils.Helper::GetDayOfWeekAbbreviation(int32 dayOfWeek)
0xeee4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xeee9  ret
```
