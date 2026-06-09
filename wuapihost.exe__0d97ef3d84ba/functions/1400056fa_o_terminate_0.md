# _o_terminate_0

- ea: `0x1400056fa`
- end: `0x140005700`
- name: `_o_terminate_0`
- size: `6`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001fa0`
- `0x140002bc0`
- `0x140002cac`
- `0x140003624`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x1400056fa`

## pseudocode

```c
// attributes: thunk
__int64 o_terminate_0(void)
{
  return _o_terminate();
}

```

## disassembly

```asm
0x1400056fa  jmp     cs:__imp__o_terminate
```
