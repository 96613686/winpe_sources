# _o___stdio_common_vfprintf

- ea: `0x180099d5e`
- end: `0x180099d64`
- name: `_o___stdio_common_vfprintf`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180099f94`
- `0x180099fe8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfprintf` at `0x180099d5e`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vfprintf()
{
  return _o___stdio_common_vfprintf();
}

```

## disassembly

```asm
0x180099d5e  jmp     cs:__imp__o___stdio_common_vfprintf
```
