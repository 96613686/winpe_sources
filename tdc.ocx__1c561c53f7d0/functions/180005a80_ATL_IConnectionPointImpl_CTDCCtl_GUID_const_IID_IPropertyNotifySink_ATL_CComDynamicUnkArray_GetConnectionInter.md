# ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::GetConnectionInterface(_GUID *)

- ea: `0x180005a80`
- end: `0x180005a99`
- name: `?GetConnectionInterface@?$IConnectionPointImpl@VCTDCCtl@@$1?IID_IPropertyNotifySink@@3U_GUID@@BVCComDynamicUnkArray@ATL@@@ATL@@UEAAJPEAU_GUID@@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a80`

## pseudocode

```c
__int64 __fastcall ATL::IConnectionPointImpl<CTDCCtl,&_GUID const IID_IPropertyNotifySink,ATL::CComDynamicUnkArray>::GetConnectionInterface(
        __int64 a1,
        GUID *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147500035LL;
  result = 0;
  *a2 = IID_IPropertyNotifySink;
  return result;
}

```

## disassembly

```asm
0x180005a80  test    rdx, rdx
0x180005a83  jnz     short loc_180005A8B
0x180005a85  mov     eax, 80004003h
0x180005a8a  retn
0x180005a8b  movups  xmm0, xmmword ptr cs:IID_IPropertyNotifySink.Data1
0x180005a92  xor     eax, eax
0x180005a94  movdqu  xmmword ptr [rdx], xmm0
0x180005a98  retn
```
