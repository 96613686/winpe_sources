# ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140005bb0`
- end: `0x140005c4b`
- name: `?Invoke@?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400050b8`
- `0x140005bb0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::Invoke(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        LCID a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rcx
  __int64 result; // rax

  v11 = qword_1400151E8;
  if ( !qword_1400151E8 || (result = 0, !qword_1400151F8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IWMPRichPreviewLauncher,&__s_GUID const _GUID_f826a914_4075_4672_8312_5f91cdf3c69e,&__s_GUID const _GUID_fa258721_cf24_45d7_a9cb_80047d7fec35,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_1400151E8;
  }
  if ( v11 )
    return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)v11 + 88LL))(
             v11,
             a1,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x140005bb0  mov     [rsp+arg_0], rbx
0x140005bb5  push    rdi
0x140005bb6  sub     rsp, 50h
0x140005bba  mov     rdi, rcx
0x140005bbd  mov     ebx, edx
0x140005bbf  mov     rcx, cs:qword_1400151E8
0x140005bc6  test    rcx, rcx
0x140005bc9  jz      short loc_140005BD6
0x140005bcb  xor     eax, eax
0x140005bcd  cmp     cs:qword_1400151F8, rax
0x140005bd4  jnz     short loc_140005BEC
0x140005bd6  mov     edx, r9d; lcid
0x140005bd9  lea     rcx, ?_tih@?$IDispatchImpl@UIWMPRichPreviewLauncher@@$1?_GUID_f826a914_4075_4672_8312_5f91cdf3c69e@@3U__s_GUID@@B$1?_GUID_fa258721_cf24_45d7_a9cb_80047d7fec35@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005be0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005be5  mov     rcx, cs:qword_1400151E8
0x140005bec  test    rcx, rcx
0x140005bef  jz      short loc_140005C40
0x140005bf1  mov     rdx, [rsp+58h+arg_40]
0x140005bf9  mov     r8d, ebx
0x140005bfc  mov     rax, [rcx]
0x140005bff  movzx   r9d, [rsp+58h+arg_20]
0x140005c08  mov     [rsp+58h+var_20], rdx
0x140005c0d  mov     rdx, [rsp+58h+arg_38]
0x140005c15  mov     rax, [rax+58h]
0x140005c19  mov     [rsp+58h+var_28], rdx
0x140005c1e  mov     rdx, [rsp+58h+arg_30]
0x140005c26  mov     [rsp+58h+var_30], rdx
0x140005c2b  mov     rdx, [rsp+58h+arg_28]
0x140005c33  mov     [rsp+58h+var_38], rdx
0x140005c38  mov     rdx, rdi
0x140005c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c40  mov     rbx, [rsp+58h+arg_0]
0x140005c45  add     rsp, 50h
0x140005c49  pop     rdi
0x140005c4a  retn
```
