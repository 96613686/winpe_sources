# _o___stdio_common_vsprintf_s_0

- ea: `0x18008fa23`
- end: `0x18008fa29`
- name: `_o___stdio_common_vsprintf_s_0`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180015ea8`
- `0x1800748ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf_s` at `0x18008fa23`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vsprintf_s_0()
{
  return _o___stdio_common_vsprintf_s();
}

```

## disassembly

```asm
0x18008fa23  jmp     cs:__imp__o___stdio_common_vsprintf_s
```
