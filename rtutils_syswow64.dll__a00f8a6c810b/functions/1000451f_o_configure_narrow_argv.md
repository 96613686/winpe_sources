# __o__configure_narrow_argv

- ea: `0x1000451f`
- end: `0x10004525`
- name: `__o__configure_narrow_argv`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x10003df8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x1000451f`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl _o__configure_narrow_argv(_crt_argv_mode mode)
{
  return __configure_narrow_argv(mode);
}

```

## disassembly

```asm
0x1000451f  jmp     ds:__imp___configure_narrow_argv
```
