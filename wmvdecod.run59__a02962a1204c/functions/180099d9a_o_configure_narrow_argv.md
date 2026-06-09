# _o__configure_narrow_argv

- ea: `0x180099d9a`
- end: `0x180099da0`
- name: `_o__configure_narrow_argv`
- size: `6`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18009960c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x180099d9a`

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
0x180099d9a  jmp     cs:__imp__o__configure_narrow_argv
```
