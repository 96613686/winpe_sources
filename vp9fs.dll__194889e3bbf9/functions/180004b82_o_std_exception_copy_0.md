# _o___std_exception_copy_0

- ea: `0x180004b82`
- end: `0x180004b88`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180005bbc`
- `0x180005d98`
- `0x18000bf48`
- `0x18000bf9c`
- `0x18000bfe0`
- `0x18000c04c`
- `0x18000c090`
- `0x18000c0f0`
- `0x18001d870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180004b82`

## pseudocode

```c
// attributes: thunk
__int64 o___std_exception_copy_0()
{
  return _o___std_exception_copy();
}

```

## disassembly

```asm
0x180004b82  jmp     cs:__imp__o___std_exception_copy
```
