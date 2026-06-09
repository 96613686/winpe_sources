# ATL::CComObject<CTDCCtl>::~CComObject<CTDCCtl>(void)

- ea: `0x18000efb8`
- end: `0x18000f0a8`
- name: `??1?$CComObject@VCTDCCtl@@@ATL@@UEAA@XZ`
- size: `240`
- prototype: `__int64 __fastcall(CTDCCtl *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f130`

## callees

- `0x180002970`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComObject<CTDCCtl>::~CComObject<CTDCCtl>(CTDCCtl *this)
{
  *((_DWORD *)this + 76) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CComControlBase'};
  *((_QWORD *)this + 13) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
  *((_QWORD *)this + 22) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CStockPropImpl<CTDCCtl,ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 23) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 24) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleControlImpl<CTDCCtl>'};
  *((_QWORD *)this + 25) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleObjectImpl<CTDCCtl>'};
  *((_QWORD *)this + 26) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceActiveObjectImpl<CTDCCtl>'};
  *((_QWORD *)this + 27) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IViewObjectExImpl<CTDCCtl>'};
  *((_QWORD *)this + 28) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>'};
  *((_QWORD *)this + 29) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPersistPropertyBagImpl<CTDCCtl>'};
  *((_QWORD *)this + 30) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IRunnableObjectImpl<CTDCCtl>'};
  *((_QWORD *)this + 31) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IConnectionPointContainerImpl<CTDCCtl>'};
  *((_QWORD *)this + 32) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPropertyNotifySinkCP<CTDCCtl,ATL::CComDynamicUnkArray>'};
  *((_QWORD *)this + 35) = &ATL::CComObject<CTDCCtl>::`vftable'{for `CProxyITDCCtlEvents<CTDCCtl>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CTDCCtl::~CTDCCtl(this);
}

```

## disassembly

```asm
0x18000efb8  push    rbx
0x18000efba  sub     rsp, 20h
0x18000efbe  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6BCComControlBase@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CComControlBase'}
0x18000efc5  mov     dword ptr [rcx+130h], 0C0000001h
0x18000efcf  mov     [rcx], rax
0x18000efd2  mov     rbx, rcx
0x18000efd5  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x18000efdc  mov     [rcx+68h], rax
0x18000efe0  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$CStockPropImpl@VCTDCCtl@@UITDCCtl@@$1?IID_ITDCCtl@@3U_GUID@@B$1?LIBID_TDCLib@@3U4@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CStockPropImpl<CTDCCtl,ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'}
0x18000efe7  mov     [rcx+0B0h], rax
0x18000efee  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_CTDCCtl@@3U_GUID@@B$1?IID_ITDCCtlEvents@@3U2@B$1?LIBID_TDCLib@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'}
0x18000eff5  mov     [rcx+0B8h], rax
0x18000effc  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleControlImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleControlImpl<CTDCCtl>'}
0x18000f003  mov     [rcx+0C0h], rax
0x18000f00a  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleObjectImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleObjectImpl<CTDCCtl>'}
0x18000f011  mov     [rcx+0C8h], rax
0x18000f018  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleInPlaceActiveObjectImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceActiveObjectImpl<CTDCCtl>'}
0x18000f01f  mov     [rcx+0D0h], rax
0x18000f026  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IViewObjectExImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IViewObjectExImpl<CTDCCtl>'}
0x18000f02d  mov     [rcx+0D8h], rax
0x18000f034  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleInPlaceObjectWindowlessImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>'}
0x18000f03b  mov     [rcx+0E0h], rax
0x18000f042  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IPersistPropertyBagImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPersistPropertyBagImpl<CTDCCtl>'}
0x18000f049  mov     [rcx+0E8h], rax
0x18000f050  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IRunnableObjectImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IRunnableObjectImpl<CTDCCtl>'}
0x18000f057  mov     [rcx+0F0h], rax
0x18000f05e  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IConnectionPointContainerImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IConnectionPointContainerImpl<CTDCCtl>'}
0x18000f065  mov     [rcx+0F8h], rax
0x18000f06c  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IPropertyNotifySinkCP@VCTDCCtl@@VCComDynamicUnkArray@ATL@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPropertyNotifySinkCP<CTDCCtl,ATL::CComDynamicUnkArray>'}
0x18000f073  mov     [rcx+100h], rax
0x18000f07a  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$CProxyITDCCtlEvents@VCTDCCtl@@@@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `CProxyITDCCtlEvents<CTDCCtl>'}
0x18000f081  mov     [rcx+118h], rax
0x18000f088  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000f08f  mov     rax, [rcx]
0x18000f092  mov     rax, [rax+10h]
0x18000f096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f09b  mov     rcx, rbx; this
0x18000f09e  add     rsp, 20h
0x18000f0a2  pop     rbx
0x18000f0a3  jmp     ??1CTDCCtl@@UEAA@XZ; CTDCCtl::~CTDCCtl(void)
```
