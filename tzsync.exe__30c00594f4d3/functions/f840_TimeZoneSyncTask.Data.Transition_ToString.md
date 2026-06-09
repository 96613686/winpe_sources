# TimeZoneSyncTask.Data.Transition::ToString

- ea: `0xf840`
- end: `0xf8d4`
- name: `TimeZoneSyncTask.Data.Transition::ToString`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0xf720`
- `0xf740`
- `0xf760`
- `0xf780`
- `0xf840`

## pseudocode

```c

```

## disassembly

```asm
0xf840  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf845  ldstr    a0WithUtcoff1Ls// "{0} with UtcOff: {1}, LstOff: {2}"
0xf84a  ldarg.0
0xf84b  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0xf850  stloc.2
0xf851  ldloca.s 2
0xf853  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf858  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf85d  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0xf862  ldarg.0
0xf863  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_UtcOffset()
0xf868  stloc.3
0xf869  ldloca.s 3
0xf86b  ldstr    aC// "c"
0xf870  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf875  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf87a  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0xf87f  ldarg.0
0xf880  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0xf885  stloc.3
0xf886  ldloca.s 3
0xf888  ldstr    aC// "c"
0xf88d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf892  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf897  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0xf89c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object, object)
0xf8a1  stloc.0
0xf8a2  ldarg.0
0xf8a3  call     instance valuetype TimeZoneSyncTask.Data.MidnightTransitionType TimeZoneSyncTask.Data.Transition::get_Type()
0xf8a8  stloc.s  4
0xf8aa  ldloc.s  4
0xf8ac  ldc.i4.1
0xf8ad  beq.s    loc_F8B6
0xf8af  ldloc.s  4
0xf8b1  ldc.i4.2
0xf8b2  beq.s    loc_F8BE
0xf8b4  br.s     loc_F8C6
0xf8b6  ldstr    a0000// " @ 00:00"
0xf8bb  stloc.1
0xf8bc  br.s     loc_F8CC
0xf8be  ldstr    a2400// " @ 24:00"
0xf8c3  stloc.1
0xf8c4  br.s     loc_F8CC
0xf8c6  ldsfld   string [mscorlib]System.String::Empty
0xf8cb  stloc.1
0xf8cc  ldloc.0
0xf8cd  ldloc.1
0xf8ce  call     string [mscorlib]System.String::Concat(string, string)
0xf8d3  ret
```
