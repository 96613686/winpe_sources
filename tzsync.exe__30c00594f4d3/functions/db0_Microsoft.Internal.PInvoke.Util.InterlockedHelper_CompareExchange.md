# Microsoft.Internal.PInvoke.Util.InterlockedHelper::CompareExchange

- ea: `0xdb0`
- end: `0xdc6`
- name: `Microsoft.Internal.PInvoke.Util.InterlockedHelper::CompareExchange`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x13100`

## callees

- `0xdb0`

## pseudocode

```c

```

## disassembly

```asm
0xdb0  ldarg.0
0xdb1  ldarg.2
0xdb2  ldarg.1
0xdb3  ldind.i8
0xdb4  call     int64 [mscorlib]System.Threading.Interlocked::CompareExchange(int64&, int64, int64)
0xdb9  stloc.0
0xdba  ldloc.0
0xdbb  ldarg.1
0xdbc  ldind.i8
0xdbd  bne.un.s loc_DC1
0xdbf  ldc.i4.1
0xdc0  ret
0xdc1  ldarg.1
0xdc2  ldloc.0
0xdc3  stind.i8
0xdc4  ldc.i4.0
0xdc5  ret
```
