# __imp_load_CreateLinkFileExWorker

- ea: `0x18000ecd4`
- end: `0x18000ece0`
- name: `__imp_load_CreateLinkFileExWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateLinkFileExWorker` at `0x18000ecd4`

## pseudocode

```c
__int64 load_CreateLinkFileExWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ecd4  lea     rax, __imp_CreateLinkFileExWorker
0x18000ecdb  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
