# _o___stdio_common_vfprintf

- ea: `0x1800118de`
- end: `0x1800118e4`
- name: `_o___stdio_common_vfprintf`
- size: `6`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180011af4`
- `0x180011b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfprintf` at `0x1800118de`

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
0x1800118de  jmp     cs:__imp__o___stdio_common_vfprintf
```
