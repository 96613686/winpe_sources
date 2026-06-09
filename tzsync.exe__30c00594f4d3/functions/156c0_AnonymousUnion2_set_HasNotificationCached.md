# AnonymousUnion2::set_HasNotificationCached

- ea: `0x156c0`
- end: `0x156d5`
- name: `AnonymousUnion2::set_HasNotificationCached`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14930`

## callees

- `0xb90`

## pseudocode

```c

```

## disassembly

```asm
0x156c0  ldarg.0
0x156c1  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x156c6  ldsfld   valuetype Section AnonymousUnion2::HasNotificationCachedSection
0x156cb  ldarg.1
0x156cc  ldc.i4.0
0x156cd  cgt.un
0x156cf  call     instance void Microsoft.Internal.PInvoke.Util.BitVector32Light::set_Item(valuetype Section section, int32 value)
0x156d4  ret
```
