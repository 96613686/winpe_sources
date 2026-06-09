# __scrt_dllmain_uninitialize_c

- ea: `0x1800016d0`
- end: `0x180001700`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001258`

## callees

- `0x1800016d0`
- `0x180001c54`
- `0x180001cae`
- `0x180001cc6`
- `0x180002dc0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = ATL::CComCoClass<CTapiLuaLib,&_GUID const CLSID_CTapiLuaLib>::GetCategoryMap();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800016d0  sub     rsp, 28h
0x1800016d4  call    __scrt_is_ucrt_dll_in_use
0x1800016d9  test    eax, eax
0x1800016db  jz      short loc_1800016ED
0x1800016dd  lea     rcx, Table; Table
0x1800016e4  add     rsp, 28h
0x1800016e8  jmp     _execute_onexit_table
0x1800016ed  call    ?GetCategoryMap@?$CComCoClass@VCTapiLuaLib@@$1?CLSID_CTapiLuaLib@@3U_GUID@@B@ATL@@SAPEBU_ATL_CATMAP_ENTRY@2@XZ; ATL::CComCoClass<CTapiLuaLib,&_GUID const CLSID_CTapiLuaLib>::GetCategoryMap(void)
0x1800016f2  test    eax, eax
0x1800016f4  jnz     short loc_1800016FB
0x1800016f6  call    _o__cexit_0
0x1800016fb  add     rsp, 28h
0x1800016ff  retn
```
