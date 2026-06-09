# _o__configure_narrow_argv_0

- ea: `0x180021c06`
- end: `0x180021c0c`
- name: `_o__configure_narrow_argv_0`
- size: `6`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800211a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__configure_narrow_argv` at `0x180021c06`

## pseudocode

```c
// attributes: thunk
errno_t __cdecl o__configure_narrow_argv_0(_crt_argv_mode mode)
{
  return _configure_narrow_argv(mode);
}

```

## disassembly

```asm
0x180021c06  jmp     cs:__imp__configure_narrow_argv
```
