# TimeZoneSyncTask.Utils.Helper::FromTzdbDate

- ea: `0xe980`
- end: `0xea38`
- name: `TimeZoneSyncTask.Utils.Helper::FromTzdbDate`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x10b80`

## callees

- `0xe980`
- `0xec70`
- `0xec90`
- `0xee20`
- `0xee40`
- `0xee60`
- `0xf5e0`
- `0xf600`

## pseudocode

```c

```

## disassembly

```asm
0xe980  ldarga.s 2
0xe982  call     instance valuetype TimeZoneSyncTask.Data.DayType TimeZoneSyncTask.Data.DayOfMonth::get_Type()
0xe987  stloc.1
0xe988  ldloc.1
0xe989  ldc.i4.1
0xe98a  beq.s    loc_E992
0xe98c  ldloc.1
0xe98d  ldc.i4.2
0xe98e  beq.s    loc_E9C7
0xe990  br.s     loc_E9FC
0xe992  ldloca.s 0
0xe994  ldarg.0
0xe995  ldarg.1
0xe996  ldarga.s 2
0xe998  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_Day()
0xe99d  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0xe9a2  br.s     loc_E9B5
0xe9a4  ldloca.s 0
0xe9a6  ldc.r8   1.0
0xe9af  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xe9b4  stloc.0
0xe9b5  ldloca.s 0
0xe9b7  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0xe9bc  ldarga.s 2
0xe9be  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_DayOfWeek()
0xe9c3  bne.un.s loc_E9A4
0xe9c5  br.s     loc_EA0C
0xe9c7  ldloca.s 0
0xe9c9  ldarg.0
0xe9ca  ldarg.1
0xe9cb  ldarg.0
0xe9cc  ldarg.1
0xe9cd  call     int32 [mscorlib]System.DateTime::DaysInMonth(int32, int32)
0xe9d2  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0xe9d7  br.s     loc_E9EA
0xe9d9  ldloca.s 0
0xe9db  ldc.r8   -1.0
0xe9e4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xe9e9  stloc.0
0xe9ea  ldloca.s 0
0xe9ec  call     instance valuetype [mscorlib]System.DayOfWeek [mscorlib]System.DateTime::get_DayOfWeek()
0xe9f1  ldarga.s 2
0xe9f3  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_DayOfWeek()
0xe9f8  bne.un.s loc_E9D9
0xe9fa  br.s     loc_EA0C
0xe9fc  ldloca.s 0
0xe9fe  ldarg.0
0xe9ff  ldarg.1
0xea00  ldarga.s 2
0xea02  call     instance int32 TimeZoneSyncTask.Data.DayOfMonth::get_Day()
0xea07  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0xea0c  ldloca.s 2
0xea0e  initobj  TimeZoneSyncTask.Data.DateTimeEx
0xea14  ldloca.s 2
0xea16  ldloc.0
0xea17  ldarga.s 3
0xea19  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeOfDay::get_Duration()
0xea1e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xea23  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Time(valuetype [mscorlib]System.DateTime value)
0xea28  ldloca.s 2
0xea2a  ldarga.s 3
0xea2c  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.TimeOfDay::get_Base()
0xea31  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Base(valuetype TimeZoneSyncTask.Data.TimeBase value)
0xea36  ldloc.2
0xea37  ret
```
