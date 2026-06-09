# __imp_load_RsopAccessCheckByTypeWorker

- ea: `0x18000f972`
- end: `0x18000f97e`
- name: `__imp_load_RsopAccessCheckByTypeWorker`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000f712`

## import_xrefs

- `ext-ms-win-profile-userenv-l1-1-0!RsopAccessCheckByTypeWorker` at `0x18000f972`

## pseudocode

```c
__int64 load_RsopAccessCheckByTypeWorker()
{
  return _tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll();
}

```

## disassembly

```asm
0x18000f972  lea     rax, __imp_RsopAccessCheckByTypeWorker
0x18000f979  jmp     __tailMerge_ext_ms_win_profile_userenv_l1_1_0_dll
```
