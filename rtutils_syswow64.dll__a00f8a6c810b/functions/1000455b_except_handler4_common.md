# __except_handler4_common

- ea: `0x1000455b`
- end: `0x10004561`
- name: `__except_handler4_common`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x10003c50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_except_handler4_common` at `0x1000455b`

## pseudocode

```c
// attributes: thunk
int _except_handler4_common()
{
  return __except_handler4_common();
}

```

## disassembly

```asm
0x1000455b  jmp     ds:__imp___except_handler4_common
```
