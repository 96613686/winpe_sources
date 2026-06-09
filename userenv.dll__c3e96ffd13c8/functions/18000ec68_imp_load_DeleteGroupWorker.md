# __imp_load_DeleteGroupWorker

- ea: `0x18000ec68`
- end: `0x18000ec74`
- name: `__imp_load_DeleteGroupWorker`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000ea62`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!DeleteGroupWorker` at `0x18000ec68`

## pseudocode

```c
__int64 load_DeleteGroupWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000ec68  lea     rax, __imp_DeleteGroupWorker
0x18000ec6f  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
