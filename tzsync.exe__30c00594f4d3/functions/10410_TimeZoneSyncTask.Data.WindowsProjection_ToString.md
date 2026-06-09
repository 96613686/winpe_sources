# TimeZoneSyncTask.Data.WindowsProjection::ToString

- ea: `0x10410`
- end: `0x104b6`
- name: `TimeZoneSyncTask.Data.WindowsProjection::ToString`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x102e0`
- `0x10300`
- `0x10320`
- `0x10340`
- `0x10410`

## pseudocode

```c

```

## disassembly

```asm
0x10410  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10415  ldstr    aUtcoff0Lstoff1// "UtcOff: {0}, LstOff: {1}, Dlt: {2}, Std"...
0x1041a  ldc.i4.4
0x1041b  newarr   [mscorlib]System.Object
0x10420  dup
0x10421  ldc.i4.0
0x10422  ldarg.0
0x10423  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsUtcOffset()
0x10428  box      [mscorlib]System.TimeSpan
0x1042d  stelem.ref
0x1042e  dup
0x1042f  ldc.i4.1
0x10430  ldarg.0
0x10431  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjection::get_TsLocalStandardOffset()
0x10436  box      [mscorlib]System.TimeSpan
0x1043b  stelem.ref
0x1043c  dup
0x1043d  ldc.i4.2
0x1043e  ldarg.0
0x1043f  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x10444  stloc.0
0x10445  ldloca.s 0
0x10447  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1044c  brtrue.s loc_10455
0x1044e  ldstr    aNone// "<none>"
0x10453  br.s     loc_10475
0x10455  ldarg.0
0x10456  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x1045b  stloc.0
0x1045c  ldloca.s 0
0x1045e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x10463  stloc.1
0x10464  ldloca.s 1
0x10466  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1046b  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x10470  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x10475  stelem.ref
0x10476  dup
0x10477  ldc.i4.3
0x10478  ldarg.0
0x10479  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x1047e  stloc.0
0x1047f  ldloca.s 0
0x10481  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x10486  brtrue.s loc_1048F
0x10488  ldstr    aNone// "<none>"
0x1048d  br.s     loc_104AF
0x1048f  ldarg.0
0x10490  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x10495  stloc.0
0x10496  ldloca.s 0
0x10498  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x1049d  stloc.1
0x1049e  ldloca.s 1
0x104a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x104a5  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x104aa  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x104af  stelem.ref
0x104b0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x104b5  ret
```
