# _o___std_exception_copy_0

- ea: `0x180002f52`
- end: `0x180002f58`
- name: `_o___std_exception_copy_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800045a4`
- `0x180004780`
- `0x18000fd5c`
- `0x18000fda0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___std_exception_copy` at `0x180002f52`

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
0x180002f52  jmp     cs:__imp__o___std_exception_copy
```
