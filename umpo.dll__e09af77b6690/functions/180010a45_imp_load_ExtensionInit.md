# __imp_load_ExtensionInit

- ea: `0x180010a45`
- end: `0x180010a51`
- name: `__imp_load_ExtensionInit`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800109c6`

## import_xrefs

- `ext-ms-win-umpoext-umpo-l1-1-0!ExtensionInit` at `0x180010a45`

## pseudocode

```c
__int64 load_ExtensionInit()
{
  return _tailMerge_ext_ms_win_umpoext_umpo_l1_1_0_dll();
}

```

## disassembly

```asm
0x180010a45  lea     rax, __imp_ExtensionInit
0x180010a4c  jmp     __tailMerge_ext_ms_win_umpoext_umpo_l1_1_0_dll
```
