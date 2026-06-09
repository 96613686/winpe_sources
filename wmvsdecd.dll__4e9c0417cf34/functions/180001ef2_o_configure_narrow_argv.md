# _o__configure_narrow_argv

- ea: `0x180001ef2`
- end: `0x180001ef8`
- name: `_o__configure_narrow_argv`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800016fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x180001ef2`

## pseudocode

```c
// attributes: thunk
__int64 o__configure_narrow_argv()
{
  return _o__configure_narrow_argv();
}

```

## disassembly

```asm
0x180001ef2  jmp     cs:__imp__o__configure_narrow_argv
```
