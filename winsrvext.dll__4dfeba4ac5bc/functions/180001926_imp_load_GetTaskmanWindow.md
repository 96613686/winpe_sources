# __imp_load_GetTaskmanWindow

- ea: `0x180001926`
- end: `0x180001932`
- name: `__imp_load_GetTaskmanWindow`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000146f`

## import_xrefs

- `USER32!GetTaskmanWindow` at `0x180001926`

## pseudocode

```c
__int64 load_GetTaskmanWindow()
{
  return _tailMerge_user32_dll();
}

```

## disassembly

```asm
0x180001926  lea     rax, __imp_GetTaskmanWindow
0x18000192d  jmp     __tailMerge_user32_dll
```
