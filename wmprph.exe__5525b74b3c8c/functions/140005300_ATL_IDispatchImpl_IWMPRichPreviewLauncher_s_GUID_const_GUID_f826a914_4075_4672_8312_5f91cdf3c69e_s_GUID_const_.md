# ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140005300`
- end: `0x14000536e`
- name: `?GetTypeInfo@?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400050b8`
- `0x140005300`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        __int64 *a4)
{
  __int64 result; // rax
  __int64 v6; // rcx

  if ( a2 )
    return 2147614731LL;
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  result = 0;
  v6 = qword_1400151E8;
  if ( !qword_1400151E8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1400151E8;
  }
  *a4 = v6;
  if ( qword_1400151E8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1400151E8 + 8LL))(qword_1400151E8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005300  push    rbx
0x140005302  sub     rsp, 20h
0x140005306  mov     rbx, r9
0x140005309  test    edx, edx
0x14000530b  jz      short loc_140005314
0x14000530d  mov     eax, 8002000Bh
0x140005312  jmp     short loc_140005368
0x140005314  test    rbx, rbx
0x140005317  jnz     short loc_140005320
0x140005319  mov     eax, 80004003h
0x14000531e  jmp     short loc_140005368
0x140005320  mov     qword ptr [r9], 0
0x140005327  xor     eax, eax
0x140005329  mov     rcx, cs:qword_1400151E8
0x140005330  test    rcx, rcx
0x140005333  jnz     short loc_14000534B
0x140005335  mov     edx, r8d; lcid
0x140005338  lea     rcx, ?_tih@?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x14000533f  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005344  mov     rcx, cs:qword_1400151E8
0x14000534b  mov     [rbx], rcx
0x14000534e  mov     rcx, cs:qword_1400151E8
0x140005355  test    rcx, rcx
0x140005358  jz      short loc_140005368
0x14000535a  mov     rax, [rcx]
0x14000535d  mov     rax, [rax+8]
0x140005361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005366  xor     eax, eax
0x140005368  add     rsp, 20h
0x14000536c  pop     rbx
0x14000536d  retn
```
