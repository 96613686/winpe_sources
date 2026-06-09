# Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateMaskFromHighValue

- ea: `0xd00`
- end: `0xd33`
- name: `Microsoft.Internal.PInvoke.Util.BitVector32Light::CreateMaskFromHighValue`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xd40`

## callees

- `0xd00`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldc.i4.s 0x10
0xd02  stloc.0
0xd03  br.s     loc_D10
0xd05  ldloc.0
0xd06  ldc.i4.1
0xd07  sub
0xd08  conv.i2
0xd09  stloc.0
0xd0a  ldarg.0
0xd0b  ldc.i4.1
0xd0c  shl
0xd0d  conv.i2
0xd0e  starg.s  0
0xd10  ldarg.0
0xd11  ldc.i4   0x8000
0xd16  and
0xd17  brfalse.s loc_D05
0xd19  ldc.i4.0
0xd1a  stloc.1
0xd1b  br.s     loc_D2C
0xd1d  ldloc.0
0xd1e  ldc.i4.1
0xd1f  sub
0xd20  conv.i2
0xd21  stloc.0
0xd22  ldloc.1
0xd23  ldc.i4.1
0xd24  shl
0xd25  conv.u2
0xd26  stloc.1
0xd27  ldloc.1
0xd28  ldc.i4.1
0xd29  or
0xd2a  conv.u2
0xd2b  stloc.1
0xd2c  ldloc.0
0xd2d  ldc.i4.0
0xd2e  bgt.s    loc_D1D
0xd30  ldloc.1
0xd31  conv.i2
0xd32  ret
```
