# TimeZoneSyncTask.Core.IanaRuleTransform::GetLocalTimeOfDay

- ea: `0x10dc0`
- end: `0x10dfb`
- name: `TimeZoneSyncTask.Core.IanaRuleTransform::GetLocalTimeOfDay`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10b80`

## callees

- `0xf5e0`
- `0xf600`
- `0x10dc0`

## pseudocode

```c

```

## disassembly

```asm
0x10dc0  ldarga.s 0
0x10dc2  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.TimeOfDay::get_Base()
0x10dc7  stloc.0
0x10dc8  ldloc.0
0x10dc9  brfalse.s loc_10DD1
0x10dcb  ldloc.0
0x10dcc  ldc.i4.1
0x10dcd  beq.s    loc_10DD9
0x10dcf  br.s     loc_10DE7
0x10dd1  ldarga.s 0
0x10dd3  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeOfDay::get_Duration()
0x10dd8  ret
0x10dd9  ldarga.s 0
0x10ddb  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeOfDay::get_Duration()
0x10de0  ldarg.2
0x10de1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x10de6  ret
0x10de7  ldarga.s 0
0x10de9  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeOfDay::get_Duration()
0x10dee  ldarg.1
0x10def  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x10df4  ldarg.2
0x10df5  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x10dfa  ret
```
