# __imp_load_PostThreadMessageW

- ea: `0x180001992`
- end: `0x18000199e`
- name: `__imp_load_PostThreadMessageW`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x180001992`

## pseudocode

```c
__int64 load_PostThreadMessageW()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180001992  lea     rax, __imp_PostThreadMessageW
0x180001999  jmp     __tailMerge_user32_dll
```
