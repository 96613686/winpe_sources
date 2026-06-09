# TimeZoneSyncTask.Data.Rule::Equals_0

- ea: `0xf540`
- end: `0xf569`
- name: `TimeZoneSyncTask.Data.Rule::Equals_0`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0xf520`

## callees

- `0xf4e0`
- `0xf500`
- `0xf540`

## pseudocode

```c

```

## disassembly

```asm
0xf540  ldarg.0
0xf541  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0xf546  ldarga.s 1
0xf548  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0xf54d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf552  brfalse.s loc_F567
0xf554  ldarg.0
0xf555  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Rule::get_LocalStandardOffset()
0xf55a  ldarga.s 1
0xf55c  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Rule::get_LocalStandardOffset()
0xf561  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xf566  ret
0xf567  ldc.i4.0
0xf568  ret
```
