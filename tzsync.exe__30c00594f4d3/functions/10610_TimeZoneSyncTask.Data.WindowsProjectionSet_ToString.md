# TimeZoneSyncTask.Data.WindowsProjectionSet::ToString

- ea: `0x10610`
- end: `0x106fa`
- name: `TimeZoneSyncTask.Data.WindowsProjectionSet::ToString`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x104d0`
- `0x10510`
- `0x10530`
- `0x10550`
- `0x10610`

## pseudocode

```c

```

## disassembly

```asm
0x10610  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10615  ldstr    aUtcoff0Dlt1Std// "UtcOff: {{{0}}}, Dlt: {{{1}}}, Std: {{{"...
0x1061a  ldc.i4.4
0x1061b  newarr   [mscorlib]System.Object
0x10620  dup
0x10621  ldc.i4.0
0x10622  ldstr    asc_17BCE// ", "
0x10627  ldarg.0
0x10628  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x1062d  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<valuetype [mscorlib]System.TimeSpan>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x10632  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.TimeSpan, string> <>c::<>9__25_0
0x10637  dup
0x10638  brtrue.s loc_10651
0x1063a  pop
0x1063b  ldsfld   class <>c <>c::<>9
0x10640  ldftn    instance string <>c::<ToString>b__25_0(valuetype [mscorlib]System.TimeSpan t)
0x10646  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.TimeSpan, string>::.ctor(object, native int)
0x1064b  dup
0x1064c  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.TimeSpan, string> <>c::<>9__25_0
0x10651  call     T0x2B000023
0x10656  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x1065b  stelem.ref
0x1065c  dup
0x1065d  ldc.i4.1
0x1065e  ldstr    asc_17BCE// ", "
0x10663  ldarg.0
0x10664  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x10669  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1066e  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, string> <>c::<>9__25_1
0x10673  dup
0x10674  brtrue.s loc_1068D
0x10676  pop
0x10677  ldsfld   class <>c <>c::<>9
0x1067c  ldftn    instance string <>c::<ToString>b__25_1(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> d)
0x10682  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, string>::.ctor(object, native int)
0x10687  dup
0x10688  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, string> <>c::<>9__25_1
0x1068d  call     T0x2B000024
0x10692  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x10697  stelem.ref
0x10698  dup
0x10699  ldc.i4.2
0x1069a  ldstr    asc_17BCE// ", "
0x1069f  ldarg.0
0x106a0  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x106a5  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x106aa  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, string> <>c::<>9__25_2
0x106af  dup
0x106b0  brtrue.s loc_106C9
0x106b2  pop
0x106b3  ldsfld   class <>c <>c::<>9
0x106b8  ldftn    instance string <>c::<ToString>b__25_2(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> d)
0x106be  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, string>::.ctor(object, native int)
0x106c3  dup
0x106c4  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, string> <>c::<>9__25_2
0x106c9  call     T0x2B000024
0x106ce  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x106d3  stelem.ref
0x106d4  dup
0x106d5  ldc.i4.3
0x106d6  ldarg.0
0x106d7  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjectionSet::get_TsLocalStandardOffset()
0x106dc  stloc.0
0x106dd  ldloca.s 0
0x106df  ldstr    aC// "c"
0x106e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x106e9  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0x106ee  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0x106f3  stelem.ref
0x106f4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x106f9  ret
```
