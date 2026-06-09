# _o___std_exception_copy_0

- ea: `0x180001fc6`
- end: `0x180001fcc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e0c`
- `0x180001e78`
- `0x180002184`
- `0x180002298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180001fc6`

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
0x180001fc6  jmp     cs:__imp__o___std_exception_copy
```
