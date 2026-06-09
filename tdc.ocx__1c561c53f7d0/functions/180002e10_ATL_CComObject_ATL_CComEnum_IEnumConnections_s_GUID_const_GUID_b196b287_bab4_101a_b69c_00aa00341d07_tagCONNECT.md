# ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::AddRef(void)

- ea: `0x180002e10`
- end: `0x180002e23`
- name: `?AddRef@?$CComObject@V?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@UEAAKXZ`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002e10`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>>::AddRef(
        __int64 a1)
{
  int v1; // edx
  __int64 result; // rax

  v1 = *(_DWORD *)(a1 + 48);
  result = 0x7FFFFFFF;
  if ( v1 != 0x7FFFFFFF )
  {
    result = (unsigned int)(v1 + 1);
    *(_DWORD *)(a1 + 48) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180002e10  mov     edx, [rcx+30h]
0x180002e13  mov     eax, 7FFFFFFFh
0x180002e18  cmp     edx, eax
0x180002e1a  jz      short locret_180002E22
0x180002e1c  lea     eax, [rdx+1]
0x180002e1f  mov     [rcx+30h], eax
0x180002e22  retn
```
