# __imp_load_CreateWindowExW

- ea: `0x180008b4a`
- end: `0x180008b56`
- name: `__imp_load_CreateWindowExW`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008a4d`

## import_xrefs

- `USER32!CreateWindowExW` at `0x180008b4a`

## pseudocode

```c
__int64 load_CreateWindowExW()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180008b4a  lea     rax, __imp_CreateWindowExW
0x180008b51  jmp     __tailMerge_user32_dll
```
