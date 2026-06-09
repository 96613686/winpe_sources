# __imp_load_CreateGroupExWorker

- ea: `0x18000ed95`
- end: `0x18000eda1`
- name: `__imp_load_CreateGroupExWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!CreateGroupExWorker` at `0x18000ed95`

## pseudocode

```c
__int64 load_CreateGroupExWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ed95  lea     rax, __imp_CreateGroupExWorker
0x18000ed9c  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
