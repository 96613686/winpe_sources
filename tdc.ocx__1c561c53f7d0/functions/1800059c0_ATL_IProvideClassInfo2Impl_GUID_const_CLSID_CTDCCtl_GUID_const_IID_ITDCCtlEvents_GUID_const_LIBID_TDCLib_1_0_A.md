# ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::GetClassInfoA(ITypeInfo * *)

- ea: `0x1800059c0`
- end: `0x180005a1b`
- name: `?GetClassInfoA@?$IProvideClassInfo2Impl@$1?CLSID_CTDCCtl@@3U_GUID@@B$1?IID_ITDCCtlEvents@@3U2@B$1?LIBID_TDCLib@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAPEAUITypeInfo@@@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800059c0`
- `0x180005e28`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::GetClassInfoA(
        __int64 a1,
        __int64 *a2)
{
  __int64 result; // rax
  __int64 v4; // rcx

  if ( !a2 )
    return 2147500035LL;
  v4 = qword_18001B1A8;
  result = 0;
  if ( !qword_18001B1A8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               0);
    v4 = qword_18001B1A8;
  }
  *a2 = v4;
  if ( qword_18001B1A8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18001B1A8 + 8LL))(qword_18001B1A8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800059c0  push    rbx
0x1800059c2  sub     rsp, 20h
0x1800059c6  mov     rbx, rdx
0x1800059c9  test    rdx, rdx
0x1800059cc  jnz     short loc_1800059D5
0x1800059ce  mov     eax, 80004003h
0x1800059d3  jmp     short loc_180005A15
0x1800059d5  mov     rcx, cs:qword_18001B1A8
0x1800059dc  xor     eax, eax
0x1800059de  test    rcx, rcx
0x1800059e1  jnz     short loc_1800059F8
0x1800059e3  xor     edx, edx; lcid
0x1800059e5  lea     rcx, ?_tih@?$IProvideClassInfo2Impl@$1?CLSID_CTDCCtl@@3U_GUID@@B$1?IID_ITDCCtlEvents@@3U2@B$1?LIBID_TDCLib@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800059ec  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800059f1  mov     rcx, cs:qword_18001B1A8
0x1800059f8  mov     [rbx], rcx
0x1800059fb  mov     rcx, cs:qword_18001B1A8
0x180005a02  test    rcx, rcx
0x180005a05  jz      short loc_180005A15
0x180005a07  mov     rax, [rcx]
0x180005a0a  mov     rax, [rax+8]
0x180005a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a13  xor     eax, eax
0x180005a15  add     rsp, 20h
0x180005a19  pop     rbx
0x180005a1a  retn
```
