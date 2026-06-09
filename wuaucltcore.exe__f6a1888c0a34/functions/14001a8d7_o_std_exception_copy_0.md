# _o___std_exception_copy_0

- ea: `0x14001a8d7`
- end: `0x14001a8dd`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140002e08`
- `0x140003b4c`
- `0x140006928`
- `0x14000696c`
- `0x1400070f8`
- `0x140014a00`
- `0x140014a7c`
- `0x140014b20`
- `0x140014b8c`
- `0x14001efd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x14001a8d7`

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
0x14001a8d7  jmp     cs:__imp__o___std_exception_copy
```
