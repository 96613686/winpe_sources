# ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140005b00`
- end: `0x140005b9b`
- name: `?Invoke@?$IDispatchImpl@UIAxWinAmbientDispatch@@$1?IID_IAxWinAmbientDispatch@@3U_GUID@@B$1?LIBID_ATLLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400050b8`
- `0x140005b00`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_140015228;
  if ( !qword_140015228 || (result = 0, !qword_140015238) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_140015228;
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
0x140005b00  mov     [rsp+arg_0], rbx
0x140005b05  push    rdi
0x140005b06  sub     rsp, 50h
0x140005b0a  mov     rdi, rcx
0x140005b0d  mov     ebx, edx
0x140005b0f  mov     rcx, cs:qword_140015228
0x140005b16  test    rcx, rcx
0x140005b19  jz      short loc_140005B26
0x140005b1b  xor     eax, eax
0x140005b1d  cmp     cs:qword_140015238, rax
0x140005b24  jnz     short loc_140005B3C
0x140005b26  mov     edx, r9d; lcid
0x140005b29  lea     rcx, ?_tih@?$IDispatchImpl@UIAxWinAmbientDispatch@@$1?IID_IAxWinAmbientDispatch@@3U_GUID@@B$1?LIBID_ATLLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x140005b30  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x140005b35  mov     rcx, cs:qword_140015228
0x140005b3c  test    rcx, rcx
0x140005b3f  jz      short loc_140005B90
0x140005b41  mov     rdx, [rsp+58h+arg_40]
0x140005b49  mov     r8d, ebx
0x140005b4c  mov     rax, [rcx]
0x140005b4f  movzx   r9d, [rsp+58h+arg_20]
0x140005b58  mov     [rsp+58h+var_20], rdx
0x140005b5d  mov     rdx, [rsp+58h+arg_38]
0x140005b65  mov     rax, [rax+58h]
0x140005b69  mov     [rsp+58h+var_28], rdx
0x140005b6e  mov     rdx, [rsp+58h+arg_30]
0x140005b76  mov     [rsp+58h+var_30], rdx
0x140005b7b  mov     rdx, [rsp+58h+arg_28]
0x140005b83  mov     [rsp+58h+var_38], rdx
0x140005b88  mov     rdx, rdi
0x140005b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b90  mov     rbx, [rsp+58h+arg_0]
0x140005b95  add     rsp, 50h
0x140005b99  pop     rdi
0x140005b9a  retn
```
