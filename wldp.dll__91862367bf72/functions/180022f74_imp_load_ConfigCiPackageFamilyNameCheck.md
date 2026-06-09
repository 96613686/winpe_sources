# __imp_load_ConfigCiPackageFamilyNameCheck

- ea: `0x180022f74`
- end: `0x180022f80`
- name: `__imp_load_ConfigCiPackageFamilyNameCheck`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x180022ef5`

## import_xrefs

- `WINTRUST!ConfigCiPackageFamilyNameCheck` at `0x180022f74`

## pseudocode

```c
__int64 load_ConfigCiPackageFamilyNameCheck()
{
  return _tailMerge_wintrust_dll();
}

```

## disassembly

```asm
0x180022f74  lea     rax, __imp_ConfigCiPackageFamilyNameCheck
0x180022f7b  jmp     __tailMerge_wintrust_dll
```
