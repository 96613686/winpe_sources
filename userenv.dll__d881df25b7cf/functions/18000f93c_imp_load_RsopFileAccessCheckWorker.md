# __imp_load_RsopFileAccessCheckWorker

- ea: `0x18000f93c`
- end: `0x18000f948`
- name: `__imp_load_RsopFileAccessCheckWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!RsopFileAccessCheckWorker` at `0x18000f93c`

## pseudocode

```c
__int64 load_RsopFileAccessCheckWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f93c  lea     rax, __imp_RsopFileAccessCheckWorker
0x18000f943  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
