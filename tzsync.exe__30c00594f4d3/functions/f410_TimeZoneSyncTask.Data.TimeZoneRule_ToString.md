# TimeZoneSyncTask.Data.TimeZoneRule::ToString

- ea: `0xf410`
- end: `0xf4c3`
- name: `TimeZoneSyncTask.Data.TimeZoneRule::ToString`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0xec60`
- `0xf2e0`
- `0xf300`
- `0xf320`
- `0xf340`
- `0xf410`

## pseudocode

```c

```

## disassembly

```asm
0xf410  ldarg.0
0xf411  call     instance valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Data.TimeZoneRule::get_Until()
0xf416  stloc.0
0xf417  ldloca.s 0
0xf419  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0xf41e  ldsfld   valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MaxValue
0xf423  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xf428  brfalse.s loc_F468
0xf42a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf42f  ldstr    aZone012// "Zone {0} {1} {2}"
0xf434  ldarg.0
0xf435  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeZoneRule::get_UtcOffset()
0xf43a  stloc.1
0xf43b  ldloca.s 1
0xf43d  ldstr    aC// "c"
0xf442  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf447  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf44c  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0xf451  ldarg.0
0xf452  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0xf457  box      TimeZoneSyncTask.Data.Rule
0xf45c  ldarg.0
0xf45d  call     instance string TimeZoneSyncTask.Data.TimeZoneRule::get_Format()
0xf462  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0xf467  ret
0xf468  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf46d  ldstr    aZone0123// "Zone {0} {1} {2} {3}"
0xf472  ldc.i4.4
0xf473  newarr   [mscorlib]System.Object
0xf478  dup
0xf479  ldc.i4.0
0xf47a  ldarg.0
0xf47b  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeZoneRule::get_UtcOffset()
0xf480  stloc.1
0xf481  ldloca.s 1
0xf483  ldstr    aC// "c"
0xf488  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf48d  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf492  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0xf497  stelem.ref
0xf498  dup
0xf499  ldc.i4.1
0xf49a  ldarg.0
0xf49b  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0xf4a0  box      TimeZoneSyncTask.Data.Rule
0xf4a5  stelem.ref
0xf4a6  dup
0xf4a7  ldc.i4.2
0xf4a8  ldarg.0
0xf4a9  call     instance string TimeZoneSyncTask.Data.TimeZoneRule::get_Format()
0xf4ae  stelem.ref
0xf4af  dup
0xf4b0  ldc.i4.3
0xf4b1  ldarg.0
0xf4b2  call     instance valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Data.TimeZoneRule::get_Until()
0xf4b7  box      TimeZoneSyncTask.Data.DateTimeEx
0xf4bc  stelem.ref
0xf4bd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf4c2  ret
```
