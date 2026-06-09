# ATL::CComCoClass<CTapiLuaLib,&_GUID const CLSID_CTapiLuaLib>::GetCategoryMap(void)

- ea: `0x180002dc0`
- end: `0x180002dc3`
- name: `?GetCategoryMap@?$CComCoClass@VCTapiLuaLib@@$1?CLSID_CTapiLuaLib@@3U_GUID@@B@ATL@@SAPEBU_ATL_CATMAP_ENTRY@2@XZ`
- size: `3`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800016d0`

## pseudocode

```c
__int64 ATL::CComCoClass<CTapiLuaLib,&_GUID const CLSID_CTapiLuaLib>::GetCategoryMap()
{
  return 0;
}

```

## disassembly

```asm
0x180002dc0  xor     eax, eax
0x180002dc2  retn
```
