# AnonymousUnion2::set_StateCached

- ea: `0x15680`
- end: `0x15695`
- name: `AnonymousUnion2::set_StateCached`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x148f0`

## callees

- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0x15680  ldarg.0
0x15681  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x15686  ldsfld   valuetype Section AnonymousUnion2::StateCachedSection
0x1568b  ldarg.1
0x1568c  ldc.i4.0
0x1568d  cgt.un
0x1568f  call     instance void Microsoft.Internal.PInvoke.Util.BitVector32Light::set_Item(valuetype Section section, int32 value)
0x15694  ret
```
