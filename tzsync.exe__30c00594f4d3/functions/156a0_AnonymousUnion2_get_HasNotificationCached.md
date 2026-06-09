# AnonymousUnion2::get_HasNotificationCached

- ea: `0x156a0`
- end: `0x156b4`
- name: `AnonymousUnion2::get_HasNotificationCached`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14910`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0x156a0  ldarg.0
0x156a1  ldflda   valuetype Microsoft.Internal.PInvoke.Util.BitVector32Light AnonymousUnion2::BitFieldEncodedData
0x156a6  ldsfld   valuetype Section AnonymousUnion2::HasNotificationCachedSection
0x156ab  call     instance int32 Microsoft.Internal.PInvoke.Util.BitVector32Light::get_Item(valuetype Section section)
0x156b0  ldc.i4.0
0x156b1  cgt.un
0x156b3  ret
```
