# __std_init_once_link_alternate_names_and_abort

- ea: `0x1800019a8`
- end: `0x1800019b3`
- name: `__std_init_once_link_alternate_names_and_abort`
- size: `11`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008634`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800019ac`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800019ac`

## pseudocode

```c
void __noreturn _std_init_once_link_alternate_names_and_abort()
{
  abort();
}

```

## disassembly

```asm
0x1800019a8  sub     rsp, 28h
0x1800019ac  call    cs:__imp_abort
```
