# _o___stdio_common_vfwprintf

- ea: `0x180099d6a`
- end: `0x180099d70`
- name: `_o___stdio_common_vfwprintf`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180099eec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfwprintf` at `0x180099d6a`

## pseudocode

```c
// attributes: thunk
__int64 o___stdio_common_vfwprintf()
{
  return _o___stdio_common_vfwprintf();
}

```

## disassembly

```asm
0x180099d6a  jmp     cs:__imp__o___stdio_common_vfwprintf
```
