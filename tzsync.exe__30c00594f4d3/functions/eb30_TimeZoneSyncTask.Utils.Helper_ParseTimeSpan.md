# TimeZoneSyncTask.Utils.Helper::ParseTimeSpan

- ea: `0xeb30`
- end: `0xebee`
- name: `TimeZoneSyncTask.Utils.Helper::ParseTimeSpan`
- size: `190`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xed40`
- `0xf6c0`
- `0x123f0`
- `0x12530`

## callees

- `0xeb30`
- `0xec20`

## pseudocode

```c

```

## disassembly

```asm
0xeb30  ldarg.0
0xeb31  ldstr    asc_1750E// "-"
0xeb36  ldc.i4.4
0xeb37  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xeb3c  stloc.0
0xeb3d  ldarg.0
0xeb3e  ldc.i4.1
0xeb3f  newarr   [mscorlib]System.Char
0xeb44  dup
0xeb45  ldc.i4.0
0xeb46  ldc.i4.s 0x2D
0xeb48  stelem.i2
0xeb49  callvirt instance string [mscorlib]System.String::TrimStart(char[])
0xeb4e  starg.s  0
0xeb50  ldc.i4.0
0xeb51  stloc.1
0xeb52  ldc.i4.0
0xeb53  stloc.2
0xeb54  ldc.i4.0
0xeb55  stloc.3
0xeb56  ldarg.0
0xeb57  callvirt instance int32 [mscorlib]System.String::get_Length()
0xeb5c  ldc.i4.0
0xeb5d  ble.s    loc_EBD6
0xeb5f  ldarg.0
0xeb60  ldc.i4.0
0xeb61  ldarg.0
0xeb62  ldstr    asc_17512// ":"
0xeb67  ldc.i4.4
0xeb68  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xeb6d  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xeb72  call     int32 TimeZoneSyncTask.Utils.Helper::ParseInt32(string s)
0xeb77  stloc.1
0xeb78  ldarg.0
0xeb79  ldarg.0
0xeb7a  ldstr    asc_17512// ":"
0xeb7f  ldc.i4.4
0xeb80  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xeb85  ldc.i4.1
0xeb86  add
0xeb87  callvirt instance string [mscorlib]System.String::Substring(int32)
0xeb8c  starg.s  0
0xeb8e  ldarg.0
0xeb8f  callvirt instance int32 [mscorlib]System.String::get_Length()
0xeb94  ldc.i4.0
0xeb95  ble.s    loc_EBD6
0xeb97  ldarg.0
0xeb98  ldc.i4.0
0xeb99  ldarg.0
0xeb9a  ldstr    asc_17512// ":"
0xeb9f  ldc.i4.4
0xeba0  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xeba5  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xebaa  call     int32 TimeZoneSyncTask.Utils.Helper::ParseInt32(string s)
0xebaf  stloc.2
0xebb0  ldarg.0
0xebb1  ldarg.0
0xebb2  ldstr    asc_17512// ":"
0xebb7  ldc.i4.4
0xebb8  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0xebbd  ldc.i4.1
0xebbe  add
0xebbf  callvirt instance string [mscorlib]System.String::Substring(int32)
0xebc4  starg.s  0
0xebc6  ldarg.0
0xebc7  callvirt instance int32 [mscorlib]System.String::get_Length()
0xebcc  ldc.i4.0
0xebcd  ble.s    loc_EBD6
0xebcf  ldarg.0
0xebd0  call     int32 TimeZoneSyncTask.Utils.Helper::ParseInt32(string s)
0xebd5  stloc.3
0xebd6  ldloca.s 4
0xebd8  ldloc.1
0xebd9  ldloc.2
0xebda  ldloc.3
0xebdb  call     instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xebe0  ldloc.0
0xebe1  brtrue.s loc_EBE6
0xebe3  ldloc.s  4
0xebe5  ret
0xebe6  ldloca.s 4
0xebe8  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Negate()
0xebed  ret
```
