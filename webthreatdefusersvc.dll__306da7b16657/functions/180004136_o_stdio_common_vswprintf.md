# _o___stdio_common_vswprintf

- ea: `0x180004136`
- end: `0x18000413c`
- name: `_o___stdio_common_vswprintf`
- size: `6`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004240`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x180004136`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vswprintf()
{
  return _o___stdio_common_vswprintf();
}

```

## disassembly

```asm
0x180004136  jmp     cs:__imp__o___stdio_common_vswprintf
```
