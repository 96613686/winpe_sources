# _o___std_exception_copy_0

- ea: `0x1800029c6`
- end: `0x1800029cc`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003300`
- `0x18000a970`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x1800029c6`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall o___std_exception_copy_0(__int64 a1)
{
  return _o___std_exception_copy(a1);
}

```

## disassembly

```asm
0x1800029c6  jmp     cs:__imp__o___std_exception_copy
```
