# TimeZoneSyncTask.Data.DstTransitionRule::ToString

- ea: `0xf1f0`
- end: `0xf2c4`
- name: `TimeZoneSyncTask.Data.DstTransitionRule::ToString`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0xe940`
- `0xf030`
- `0xf050`
- `0xf070`
- `0xf090`
- `0xf0b0`
- `0xf0d0`
- `0xf0f0`
- `0xf1f0`

## pseudocode

```c

```

## disassembly

```asm
0xf1f0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf1f5  ldstr    aRule0123456// "Rule {0} {1} {2} {3} {4} {5} {6}"
0xf1fa  ldc.i4.7
0xf1fb  newarr   [mscorlib]System.Object
0xf200  dup
0xf201  ldc.i4.0
0xf202  ldarg.0
0xf203  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_From()
0xf208  box      [mscorlib]System.Int32
0xf20d  stelem.ref
0xf20e  dup
0xf20f  ldc.i4.1
0xf210  ldarg.0
0xf211  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_From()
0xf216  ldarg.0
0xf217  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_To()
0xf21c  beq.s    loc_F251
0xf21e  ldarg.0
0xf21f  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_To()
0xf224  ldsflda  valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MaxValue
0xf229  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xf22e  beq.s    loc_F24A
0xf230  ldarg.0
0xf231  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_To()
0xf236  stloc.0
0xf237  ldloca.s 0
0xf239  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf23e  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xf243  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf248  br.s     loc_F256
0xf24a  ldstr    aMax// "max"
0xf24f  br.s     loc_F256
0xf251  ldstr    aOnly// "only"
0xf256  stelem.ref
0xf257  dup
0xf258  ldc.i4.2
0xf259  ldarg.0
0xf25a  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_In()
0xf25f  call     string TimeZoneSyncTask.Utils.Helper::GetMonthAbbreviation(int32 month)
0xf264  stelem.ref
0xf265  dup
0xf266  ldc.i4.3
0xf267  ldarg.0
0xf268  call     instance valuetype TimeZoneSyncTask.Data.DayOfMonth TimeZoneSyncTask.Data.DstTransitionRule::get_On()
0xf26d  box      TimeZoneSyncTask.Data.DayOfMonth
0xf272  stelem.ref
0xf273  dup
0xf274  ldc.i4.4
0xf275  ldarg.0
0xf276  call     instance valuetype TimeZoneSyncTask.Data.TimeOfDay TimeZoneSyncTask.Data.DstTransitionRule::get_At()
0xf27b  box      TimeZoneSyncTask.Data.TimeOfDay
0xf280  stelem.ref
0xf281  dup
0xf282  ldc.i4.5
0xf283  ldarg.0
0xf284  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.DstTransitionRule::get_Save()
0xf289  stloc.1
0xf28a  ldloca.s 1
0xf28c  ldstr    aC// "c"
0xf291  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf296  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xf29b  call     instance string [mscorlib]System.TimeSpan::ToString(string, class [mscorlib]System.IFormatProvider)
0xf2a0  stelem.ref
0xf2a1  dup
0xf2a2  ldc.i4.6
0xf2a3  ldarg.0
0xf2a4  call     instance string TimeZoneSyncTask.Data.DstTransitionRule::get_Letter()
0xf2a9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf2ae  brtrue.s loc_F2B8
0xf2b0  ldarg.0
0xf2b1  call     instance string TimeZoneSyncTask.Data.DstTransitionRule::get_Letter()
0xf2b6  br.s     loc_F2BD
0xf2b8  ldstr    asc_1750E// "-"
0xf2bd  stelem.ref
0xf2be  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xf2c3  ret
```
