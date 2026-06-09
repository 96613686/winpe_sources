# ATL::CComPolyObject<ATL::CAxHostWindow>::CComPolyObject<ATL::CAxHostWindow>(void *)

- ea: `0x140001d88`
- end: `0x140001f1c`
- name: `??0?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@QEAA@PEAX@Z`
- size: `404`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140009710`

## import_xrefs

- `USER32!DefWindowProcW` at `0x140001da1`
- `USER32!GetSysColor` at `0x140001e37`
- `USER32!GetSysColor` at `0x140001e37`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<ATL::CAxHostWindow>::CComPolyObject<ATL::CAxHostWindow>(__int64 a1)
{
  int v2; // eax
  DWORD SysColor; // eax
  unsigned int v4; // eax

  *(_QWORD *)a1 = &ATL::CComPolyObject<ATL::CAxHostWindow>::`vftable';
  *(_DWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 72) = DefWindowProcW;
  *(_DWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_QWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 352) = 0;
  v2 = *(_DWORD *)(a1 + 308);
  *(_DWORD *)(a1 + 264) &= 0xFFFFFFC0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 308) = v2 & 0xFFFFFFF8 | 3;
  SysColor = GetSysColor(8);
  *(_DWORD *)(a1 + 264) &= ~0x40u;
  *(_DWORD *)(a1 + 316) = SysColor;
  v4 = *(_DWORD *)(a1 + 308) & 0xFFFFFFAF;
  *(_DWORD *)(a1 + 320) = 1024;
  *(_DWORD *)(a1 + 260) = -842150451;
  *(_DWORD *)(a1 + 308) = v4 | 0x28;
  *(_QWORD *)(a1 + 16) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxHostWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
  *(_QWORD *)(a1 + 80) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IAxWinHostWindow'};
  *(_QWORD *)(a1 + 88) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleClientSite'};
  *(_QWORD *)(a1 + 96) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleInPlaceSiteWindowless'};
  *(_QWORD *)(a1 + 104) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleControlSite'};
  *(_QWORD *)(a1 + 112) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleContainer'};
  *(_QWORD *)(a1 + 120) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `ATL::IObjectWithSiteImpl<ATL::CAxHostWindow>'};
  *(_QWORD *)(a1 + 136) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IServiceProvider'};
  *(_QWORD *)(a1 + 144) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IAdviseSink'};
  *(_QWORD *)(a1 + 152) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IDocHostUIHandler'};
  *(_QWORD *)(a1 + 160) = &ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>'};
  *(_QWORD *)(a1 + 344) = 4;
  *(_QWORD *)(a1 + 168) = a1;
  _InterlockedIncrement(&dword_1400153D8);
  return a1;
}

```

## disassembly

```asm
0x140001d88  mov     [rsp+arg_0], rbx
0x140001d8d  push    rdi
0x140001d8e  sub     rsp, 20h
0x140001d92  xor     edi, edi
0x140001d94  lea     rax, ??_7?$CComPolyObject@VCAxHostWindow@ATL@@@ATL@@6B@; const ATL::CComPolyObject<ATL::CAxHostWindow>::`vftable'
0x140001d9b  mov     [rcx], rax
0x140001d9e  mov     rbx, rcx
0x140001da1  mov     rax, cs:__imp_DefWindowProcW
0x140001da8  mov     [rcx+8], edi
0x140001dab  mov     [rcx+48h], rax
0x140001daf  mov     [rcx+0A8h], edi
0x140001db5  mov     [rcx+18h], rdi
0x140001db9  mov     [rcx+38h], rdi
0x140001dbd  mov     [rcx+80h], rdi
0x140001dc4  mov     [rcx+0B0h], rdi
0x140001dcb  mov     [rcx+0B8h], rdi
0x140001dd2  mov     [rcx+0C0h], rdi
0x140001dd9  mov     [rcx+0C8h], rdi
0x140001de0  mov     [rcx+0D0h], rdi
0x140001de7  mov     [rcx+0D8h], rdi
0x140001dee  mov     [rcx+0E0h], rdi
0x140001df5  mov     [rcx+0E8h], rdi
0x140001dfc  mov     [rcx+148h], rdi
0x140001e03  mov     [rcx+150h], rdi
0x140001e0a  mov     [rcx+160h], rdi
0x140001e11  mov     eax, [rcx+134h]
0x140001e17  and     dword ptr [rcx+108h], 0FFFFFFC0h
0x140001e1e  and     eax, 0FFFFFFFBh
0x140001e21  or      eax, 3
0x140001e24  mov     [rcx+40h], rdi
0x140001e28  mov     [rcx+134h], eax
0x140001e2e  mov     [rcx+138h], edi
0x140001e34  lea     ecx, [rdi+8]; nIndex
0x140001e37  call    cs:__imp_GetSysColor
0x140001e3d  and     dword ptr [rbx+108h], 0FFFFFFBFh
0x140001e44  mov     [rbx+13Ch], eax
0x140001e4a  mov     eax, [rbx+134h]
0x140001e50  and     eax, 0FFFFFFAFh
0x140001e53  mov     dword ptr [rbx+140h], 400h
0x140001e5d  or      eax, 28h
0x140001e60  mov     dword ptr [rbx+104h], 0CDCDCDCDh
0x140001e6a  mov     [rbx+134h], eax
0x140001e70  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6B?$CWindowImpl@VCAxHostWindow@ATL@@VCWindow@2@V?$CWinTraits@$0FGAAAAAA@$0A@@2@@1@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `ATL::CWindowImpl<ATL::CAxHostWindow,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x140001e77  mov     [rbx+10h], rax
0x140001e7b  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIAxWinHostWindow@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IAxWinHostWindow'}
0x140001e82  mov     [rbx+50h], rax
0x140001e86  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIOleClientSite@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleClientSite'}
0x140001e8d  mov     [rbx+58h], rax
0x140001e91  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIOleInPlaceSiteWindowless@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleInPlaceSiteWindowless'}
0x140001e98  mov     [rbx+60h], rax
0x140001e9c  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIOleControlSite@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleControlSite'}
0x140001ea3  mov     [rbx+68h], rax
0x140001ea7  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIOleContainer@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IOleContainer'}
0x140001eae  mov     [rbx+70h], rax
0x140001eb2  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6B?$IObjectWithSiteImpl@VCAxHostWindow@ATL@@@1@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `ATL::IObjectWithSiteImpl<ATL::CAxHostWindow>'}
0x140001eb9  mov     [rbx+78h], rax
0x140001ebd  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIServiceProvider@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IServiceProvider'}
0x140001ec4  mov     [rbx+88h], rax
0x140001ecb  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIAdviseSink@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IAdviseSink'}
0x140001ed2  mov     [rbx+90h], rax
0x140001ed9  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6BIDocHostUIHandler@@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `IDocHostUIHandler'}
0x140001ee0  mov     [rbx+98h], rax
0x140001ee7  lea     rax, ??_7?$CComContainedObject@VCAxHostWindow@ATL@@@ATL@@6B?$IDispatchImpl@UIAxWinAmbientDispatch@@$1?IID_IAxWinAmbientDispatch@@3U_GUID@@B$1?LIBID_ATLLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComContainedObject<ATL::CAxHostWindow>::`vftable'{for `ATL::IDispatchImpl<IAxWinAmbientDispatch,&_GUID const IID_IAxWinAmbientDispatch,&_GUID const LIBID_ATLLib,1,0,ATL::CComTypeInfoHolder>'}
0x140001eee  mov     [rbx+0A0h], rax
0x140001ef5  mov     qword ptr [rbx+158h], 4
0x140001f00  mov     [rbx+0A8h], rbx
0x140001f07  lock inc cs:dword_1400153D8
0x140001f0e  mov     rax, rbx
0x140001f11  mov     rbx, [rsp+28h+arg_0]
0x140001f16  add     rsp, 20h
0x140001f1a  pop     rdi
0x140001f1b  retn
```
