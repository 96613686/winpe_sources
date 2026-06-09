# __imp_load_ucal_openCountryTimeZones

- ea: `0x180002f5f`
- end: `0x180002f6b`
- name: `__imp_load_ucal_openCountryTimeZones`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002ee0`

## import_xrefs

- `icu!ucal_openCountryTimeZones` at `0x180002f5f`

## pseudocode

```c
__int64 load_ucal_openCountryTimeZones()
{
  return _tailMerge_icu_dll();
}

```

## disassembly

```asm
0x180002f5f  lea     rax, __imp_ucal_openCountryTimeZones
0x180002f66  jmp     __tailMerge_icu_dll
```
