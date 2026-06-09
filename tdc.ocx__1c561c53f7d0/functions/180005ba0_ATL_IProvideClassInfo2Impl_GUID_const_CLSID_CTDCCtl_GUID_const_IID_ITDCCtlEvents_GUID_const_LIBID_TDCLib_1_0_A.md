# ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::GetGUID(ulong,_GUID *)

- ea: `0x180005ba0`
- end: `0x180005bcd`
- name: `?GetGUID@?$IProvideClassInfo2Impl@$1?CLSID_CTDCCtl@@3U_GUID@@B$1?IID_ITDCCtlEvents@@3U2@B$1?LIBID_TDCLib@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJKPEAU_GUID@@@Z`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005ba0`

## pseudocode

```c
__int64 __fastcall ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::GetGUID(
        __int64 a1,
        int a2,
        GUID *a3)
{
  __int64 result; // rax
  GUID v4; // xmm0

  if ( !a3 )
    return 2147500035LL;
  if ( a2 == 1 )
  {
    v4 = IID_ITDCCtlEvents;
    result = 0;
  }
  else
  {
    v4 = GUID_NULL;
    result = 2147500037LL;
  }
  *a3 = v4;
  return result;
}

```

## disassembly

```asm
0x180005ba0  test    r8, r8
0x180005ba3  jnz     short loc_180005BAB
0x180005ba5  mov     eax, 80004003h
0x180005baa  retn
0x180005bab  cmp     edx, 1
0x180005bae  jnz     short loc_180005BBB
0x180005bb0  movups  xmm0, xmmword ptr cs:IID_ITDCCtlEvents.Data1
0x180005bb7  xor     eax, eax
0x180005bb9  jmp     short loc_180005BC7
0x180005bbb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180005bc2  mov     eax, 80004005h
0x180005bc7  movdqu  xmmword ptr [r8], xmm0
0x180005bcc  retn
```
