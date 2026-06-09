# _o___std_exception_copy_0

- ea: `0x140002b3a`
- end: `0x140002b40`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140003624`
- `0x140003738`
- `0x140008058`
- `0x140008250`
- `0x1400082a4`
- `0x1400082e8`
- `0x140008354`
- `0x140008598`
- `0x1400085dc`
- `0x14000863c`
- `0x14000869c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002b3a`

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
0x140002b3a  jmp     cs:__imp__o___std_exception_copy
```
