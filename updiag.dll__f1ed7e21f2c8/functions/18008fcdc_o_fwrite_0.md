# _o_fwrite_0

- ea: `0x18008fcdc`
- end: `0x18008fce2`
- name: `_o_fwrite_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011260`
- `0x180012c04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18008fcdc`

## pseudocode

```c
// attributes: thunk
__int64 o_fwrite_0()
{
  return _o_fwrite();
}

```

## disassembly

```asm
0x18008fcdc  jmp     cs:__imp__o_fwrite
```
