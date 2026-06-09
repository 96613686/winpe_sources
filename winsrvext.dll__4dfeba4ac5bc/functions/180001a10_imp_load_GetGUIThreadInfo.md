# __imp_load_GetGUIThreadInfo

- ea: `0x180001a10`
- end: `0x180001a1c`
- name: `__imp_load_GetGUIThreadInfo`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!GetGUIThreadInfo` at `0x180001a10`

## pseudocode

```c
__int64 load_GetGUIThreadInfo()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180001a10  lea     rax, __imp_GetGUIThreadInfo
0x180001a17  jmp     __tailMerge_user32_dll
```
