# TimeZoneSyncTask.Data.DateTimeEx::FromString

- ea: `0xed40`
- end: `0xedf2`
- name: `TimeZoneSyncTask.Data.DateTimeEx::FromString`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x123f0`

## callees

- `0xce30`
- `0xeab0`
- `0xeb30`
- `0xec70`
- `0xec90`

## pseudocode

```c

```

## disassembly

```asm
0xed40  ldarg.0
0xed41  ldsfld   string TimeZoneSyncTask.Utils.Helper::TimeBaseSuffixes
0xed46  ldftn    T0x2B00001D
0xed4c  newobj   instance void class [mscorlib]System.Func`2<char, bool>::.ctor(object, native int)
0xed51  call     T0x2B00001E
0xed56  stloc.0
0xed57  ldarg.0
0xed58  ldsfld   string TimeZoneSyncTask.Utils.Helper::TimeBaseSuffixes
0xed5d  call     T0x2B00001F
0xed62  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xed67  starg.s  0
0xed69  ldarg.0
0xed6a  ldstr    aT// "T"
0xed6f  ldc.i4.4
0xed70  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xed75  ldc.i4.0
0xed76  cgt
0xed78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xed7d  ldstr    aExpectingTInTh// "expecting T in the middle, got {0}"
0xed82  ldarg.0
0xed83  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xed88  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0xed8d  ldarg.0
0xed8e  ldc.i4.0
0xed8f  ldarg.0
0xed90  ldstr    aT// "T"
0xed95  ldc.i4.4
0xed96  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xed9b  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xeda0  stloc.1
0xeda1  ldarg.0
0xeda2  ldarg.0
0xeda3  ldstr    aT// "T"
0xeda8  ldc.i4.4
0xeda9  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xedae  ldc.i4.1
0xedaf  add
0xedb0  callvirt instance string [mscorlib]System.String::Substring(int32)
0xedb5  ldloc.1
0xedb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xedbb  callvirt instance class [mscorlib]System.Globalization.DateTimeFormatInfo [mscorlib]System.Globalization.CultureInfo::get_DateTimeFormat()
0xedc0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider)
0xedc5  stloc.2
0xedc6  call     valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Utils.Helper::ParseTimeSpan(string ts)
0xedcb  stloc.3
0xedcc  ldloca.s 4
0xedce  initobj  TimeZoneSyncTask.Data.DateTimeEx
0xedd4  ldloca.s 4
0xedd6  ldloc.2
0xedd7  ldloc.3
0xedd8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xeddd  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Time(valuetype [mscorlib]System.DateTime value)
0xede2  ldloca.s 4
0xede4  ldloc.0
0xede5  call     valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Utils.Helper::FromSuffixToBase(char c)
0xedea  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Base(valuetype TimeZoneSyncTask.Data.TimeBase value)
0xedef  ldloc.s  4
0xedf1  ret
```
