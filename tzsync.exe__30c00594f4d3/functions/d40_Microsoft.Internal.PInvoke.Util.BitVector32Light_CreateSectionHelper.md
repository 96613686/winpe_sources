# Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSectionHelper

- ea: `0xd40`
- end: `0xd7b`
- name: `Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateSectionHelper`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xc10`
- `0xc20`

## callees

- `0xce0`
- `0xd00`
- `0xd40`
- `0x13ec0`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldarg.0
0xd41  ldc.i4.1
0xd42  bge.s    loc_D54
0xd44  ldstr    aMaxvalueIsTooS// "maxValue is too small"
0xd49  ldstr    aMaxvalue// "maxValue"
0xd4e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xd53  throw
0xd54  ldarg.2
0xd55  ldarg.1
0xd56  call     int16 Microsoft.Internal.PInvoke.Util.BitVector32Light::CountBitsSet(int16 mask)
0xd5b  add
0xd5c  conv.i2
0xd5d  stloc.0
0xd5e  ldloc.0
0xd5f  ldc.i4.s 0x20
0xd61  blt.s    loc_D6E
0xd63  ldstr    aBitvectorfull// "BitVectorFull"
0xd68  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xd6d  throw
0xd6e  ldarg.0
0xd6f  call     int16 Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateMaskFromHighValue(int16 highValue)
0xd74  ldloc.0
0xd75  newobj   instance void Section::.ctor(int16 mask, int16 offset)
0xd7a  ret
```
