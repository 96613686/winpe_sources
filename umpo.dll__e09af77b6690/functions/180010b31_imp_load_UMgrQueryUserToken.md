# __imp_load_UMgrQueryUserToken

- ea: `0x180010b31`
- end: `0x180010b3d`
- name: `__imp_load_UMgrQueryUserToken`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010ab2`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180010b31`

## pseudocode

```c
__int64 load_UMgrQueryUserToken()
{
  return _tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll();
}

```

## disassembly

```asm
0x180010b31  lea     rax, __imp_UMgrQueryUserToken
0x180010b38  jmp     __tailMerge_ext_ms_win_session_usermgr_l1_1_0_dll
```
