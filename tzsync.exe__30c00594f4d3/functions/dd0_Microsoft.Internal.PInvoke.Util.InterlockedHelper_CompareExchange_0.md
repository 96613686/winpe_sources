# Microsoft.Internal.PInvoke.Util.InterlockedHelper::CompareExchange_0

- ea: `0xdd0`
- end: `0xde6`
- name: `Microsoft.Internal.PInvoke.Util.InterlockedHelper::CompareExchange_0`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12fe0`

## callees

- `0xdd0`

## pseudocode

```c

```

## disassembly

```asm
0xdd0  ldarg.0
0xdd1  ldarg.2
0xdd2  ldarg.1
0xdd3  ldind.i4
0xdd4  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0xdd9  stloc.0
0xdda  ldloc.0
0xddb  ldarg.1
0xddc  ldind.i4
0xddd  bne.un.s loc_DE1
0xddf  ldc.i4.1
0xde0  ret
0xde1  ldarg.1
0xde2  ldloc.0
0xde3  stind.i4
0xde4  ldc.i4.0
0xde5  ret
```
