# ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>::Reset(void)

- ea: `0x1800089b0`
- end: `0x1800089bb`
- name: `?Reset@?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComSingleThreadModel@6@@ATL@@UEAAJXZ`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComSingleThreadModel>::Reset(
        __int64 a1)
{
  *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 16);
  return 0;
}

```

## disassembly

```asm
0x1800089b0  mov     rax, [rcx+10h]
0x1800089b4  mov     [rcx+20h], rax
0x1800089b8  xor     eax, eax
0x1800089ba  retn
```
