# wil_details_FeatureStateCache::get_VariantCached

- ea: `0x14950`
- end: `0x14966`
- name: `wil_details_FeatureStateCache::get_VariantCached`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x128c0`
- `0x13100`

## callees

- `0x156e0`

## pseudocode

```c

```

## disassembly

```asm
0x14950  ldarg.0
0x14951  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14956  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x1495b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14960  call     instance bool AnonymousUnion2::get_VariantCached()
0x14965  ret
```
