# Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateMask_0

- ea: `0xbf0`
- end: `0xc0c`
- name: `Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateMask_0`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbe0`

## callees

- `0xbf0`

## pseudocode

```c

```

## disassembly

```asm
0xbf0  ldarg.0
0xbf1  brtrue.s loc_BF5
0xbf3  ldc.i4.1
0xbf4  ret
0xbf5  ldarg.0
0xbf6  ldc.i4   0x80000000
0xbfb  bne.un.s loc_C08
0xbfd  ldstr    aBitvectorfull// "BitVectorFull"
0xc02  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xc07  throw
0xc08  ldarg.0
0xc09  ldc.i4.1
0xc0a  shl
0xc0b  ret
```
