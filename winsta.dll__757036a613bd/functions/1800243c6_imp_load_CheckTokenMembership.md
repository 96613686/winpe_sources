# __imp_load_CheckTokenMembership

- ea: `0x1800243c6`
- end: `0x1800243d2`
- name: `__imp_load_CheckTokenMembership`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002348f`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800243c6`

## pseudocode

```c
__int64 load_CheckTokenMembership()
{
  return _tailMerge_api_ms_win_security_base_l1_1_0_dll();
}

```

## disassembly

```asm
0x1800243c6  lea     rax, __imp_CheckTokenMembership
0x1800243cd  jmp     __tailMerge_api_ms_win_security_base_l1_1_0_dll
```
