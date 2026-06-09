# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::GetConnectionInterface(_GUID *)

- ea: `0x180005aa0`
- end: `0x180005ab9`
- name: `?GetConnectionInterface@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_ITDCCtlEvents@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005aa0`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_ITDCCtlEvents,ATL::CComDynamicUnkArray>::GetConnectionInterface(
        __int64 a1,
        GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = IID_ITDCCtlEvents;
  return result;
}

```

## disassembly

```asm
0x180005aa0  test    rdx, rdx
0x180005aa3  jnz     short loc_180005AAB
0x180005aa5  mov     eax, 80004003h
0x180005aaa  retn
0x180005aab  movups  xmm0, xmmword ptr cs:IID_ITDCCtlEvents.Data1
0x180005ab2  xor     eax, eax
0x180005ab4  movdqu  xmmword ptr [rdx], xmm0
0x180005ab8  retn
```
