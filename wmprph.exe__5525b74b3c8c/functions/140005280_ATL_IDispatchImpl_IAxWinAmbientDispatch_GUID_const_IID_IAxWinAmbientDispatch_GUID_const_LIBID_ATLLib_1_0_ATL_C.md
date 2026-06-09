# ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x140005280`
- end: `0x1400052ee`
- name: `?GetTypeInfo@?$IDispatchImpl@UIAxWinAmbientDispatch@@$1?IID_IAxWinAmbientDispatch@@3U_GUID@@B$1?LIBID_ATLLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400050b8`
- `0x140005280`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_140015228;
  if ( !qword_140015228 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_140015228;
  }
  *a4 = v6;
  if ( qword_140015228 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_140015228 + 8LL))(qword_140015228);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x140005280  push    rbx
0x140005282  sub     rsp, 20h
0x140005286  mov     rbx, r9
0x140005289  test    edx, edx
0x14000528b  jz      short loc_140005294
0x14000528d  mov     eax, 8002000Bh
0x140005292  jmp     short loc_1400052E8
0x140005294  test    rbx, rbx
0x140005297  jnz     short loc_1400052A0
0x140005299  mov     eax, 80004003h
0x14000529e  jmp     short loc_1400052E8
0x1400052a0  mov     qword ptr [r9], 0
0x1400052a7  xor     eax, eax
0x1400052a9  mov     rcx, cs:qword_140015228
0x1400052b0  test    rcx, rcx
0x1400052b3  jnz     short loc_1400052CB
0x1400052b5  mov     edx, r8d; lcid
0x1400052b8  lea     rcx, ?_tih@?$IDispatchImpl@UIAxWinAmbientDispatch@@$1?IID_IAxWinAmbientDispatch@@3U_GUID@@B$1?LIBID_ATLLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1400052bf  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1400052c4  mov     rcx, cs:qword_140015228
0x1400052cb  mov     [rbx], rcx
0x1400052ce  mov     rcx, cs:qword_140015228
0x1400052d5  test    rcx, rcx
0x1400052d8  jz      short loc_1400052E8
0x1400052da  mov     rax, [rcx]
0x1400052dd  mov     rax, [rax+8]
0x1400052e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052e6  xor     eax, eax
0x1400052e8  add     rsp, 20h
0x1400052ec  pop     rbx
0x1400052ed  retn
```
