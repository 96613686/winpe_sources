# _o___std_exception_copy_0

- ea: `0x140002b22`
- end: `0x140002b28`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64()`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140003604`
- `0x140003718`
- `0x140008038`
- `0x140008230`
- `0x140008284`
- `0x1400082c8`
- `0x140008334`
- `0x140008578`
- `0x1400085bc`
- `0x14000861c`
- `0x14000867c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x140002b22`

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
0x140002b22  jmp     cs:__imp__o___std_exception_copy
```
