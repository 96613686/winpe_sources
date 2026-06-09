# __scrt_dllmain_uninitialize_c

- ea: `0x1800304b0`
- end: `0x1800304e0`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180030ab0`

## callees

- `0x180004cb0`
- `0x18002fe21`
- `0x18002fe51`
- `0x1800304b0`
- `0x180030fa0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CComCoClass<CUpdatePolicyReader,&_GUID const CLSID_UpdatePolicyReader>::GetObjectDescription();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800304b0  sub     rsp, 28h
0x1800304b4  call    __scrt_is_ucrt_dll_in_use
0x1800304b9  test    eax, eax
0x1800304bb  jz      short loc_1800304CD
0x1800304bd  lea     rcx, Table; Table
0x1800304c4  add     rsp, 28h
0x1800304c8  jmp     _execute_onexit_table
0x1800304cd  call    ?GetObjectDescription@?$CComCoClass@VCUpdatePolicyReader@@$1?CLSID_UpdatePolicyReader@@3U_GUID@@B@ATL@@SAPEB_WXZ; ATL::CComCoClass<CUpdatePolicyReader,&_GUID const CLSID_UpdatePolicyReader>::GetObjectDescription(void)
0x1800304d2  test    eax, eax
0x1800304d4  jnz     short loc_1800304DB
0x1800304d6  call    _o__cexit_0
0x1800304db  add     rsp, 28h
0x1800304df  retn
```
