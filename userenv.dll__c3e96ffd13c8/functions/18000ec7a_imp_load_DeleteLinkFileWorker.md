# __imp_load_DeleteLinkFileWorker

- ea: `0x18000ec7a`
- end: `0x18000ec86`
- name: `__imp_load_DeleteLinkFileWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteLinkFileWorker` at `0x18000ec7a`

## pseudocode

```c
__int64 load_DeleteLinkFileWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ec7a  lea     rax, __imp_DeleteLinkFileWorker
0x18000ec81  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
