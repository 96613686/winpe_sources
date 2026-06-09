# ATL::IDispatchImpl<ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800071c0`
- end: `0x18000725b`
- name: `?Invoke@?$IDispatchImpl@UITDCCtl@@$1?IID_ITDCCtl@@3U_GUID@@B$1?LIBID_TDCLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005e28`
- `0x1800071c0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_18001B168;
  if ( !qword_18001B168 || (result = 0, !qword_18001B178) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_18001B168;
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
0x1800071c0  mov     [rsp+arg_0], rbx
0x1800071c5  push    rdi
0x1800071c6  sub     rsp, 50h
0x1800071ca  mov     rdi, rcx
0x1800071cd  mov     ebx, edx
0x1800071cf  mov     rcx, cs:qword_18001B168
0x1800071d6  test    rcx, rcx
0x1800071d9  jz      short loc_1800071E6
0x1800071db  xor     eax, eax
0x1800071dd  cmp     cs:qword_18001B178, rax
0x1800071e4  jnz     short loc_1800071FC
0x1800071e6  mov     edx, r9d; lcid
0x1800071e9  lea     rcx, ?_tih@?$IDispatchImpl@UITDCCtl@@$1?IID_ITDCCtl@@3U_GUID@@B$1?LIBID_TDCLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800071f0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800071f5  mov     rcx, cs:qword_18001B168
0x1800071fc  test    rcx, rcx
0x1800071ff  jz      short loc_180007250
0x180007201  mov     rdx, [rsp+58h+arg_40]
0x180007209  mov     r8d, ebx
0x18000720c  mov     rax, [rcx]
0x18000720f  movzx   r9d, [rsp+58h+arg_20]
0x180007218  mov     [rsp+58h+var_20], rdx
0x18000721d  mov     rdx, [rsp+58h+arg_38]
0x180007225  mov     rax, [rax+58h]
0x180007229  mov     [rsp+58h+var_28], rdx
0x18000722e  mov     rdx, [rsp+58h+arg_30]
0x180007236  mov     [rsp+58h+var_30], rdx
0x18000723b  mov     rdx, [rsp+58h+arg_28]
0x180007243  mov     [rsp+58h+var_38], rdx
0x180007248  mov     rdx, rdi
0x18000724b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007250  mov     rbx, [rsp+58h+arg_0]
0x180007255  add     rsp, 50h
0x180007259  pop     rdi
0x18000725a  retn
```
