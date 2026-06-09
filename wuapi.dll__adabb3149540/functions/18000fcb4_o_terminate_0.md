# _o_terminate_0

- ea: `0x18000fcb4`
- end: `0x18000fcba`
- name: `_o_terminate_0`
- size: `6`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180011a90`
- `0x180011b7c`
- `0x180011be8`
- `0x180012aec`
- `0x180012fec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18000fcb4`

## pseudocode

```c
// attributes: thunk
__int64 o_terminate_0()
{
  return _o_terminate();
}

```

## disassembly

```asm
0x18000fcb4  jmp     cs:__imp__o_terminate
```
