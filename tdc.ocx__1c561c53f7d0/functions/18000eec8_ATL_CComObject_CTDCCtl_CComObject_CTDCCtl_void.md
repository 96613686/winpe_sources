# ATL::CComObject<CTDCCtl>::CComObject<CTDCCtl>(void *)

- ea: `0x18000eec8`
- end: `0x18000efaf`
- name: `??0?$CComObject@VCTDCCtl@@@ATL@@QEAA@PEAX@Z`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010c90`

## callees

- `0x180002364`
- `0x180015010`

## pseudocode

```c
CTDCCtl *__fastcall ATL::CComObject<CTDCCtl>::CComObject<CTDCCtl>(CTDCCtl *a1)
{
  struct ATL::CAtlModule *v2; // rcx

  CTDCCtl::CTDCCtl(a1);
  v2 = ATL::_pAtlModule;
  *(_QWORD *)a1 = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CComControlBase'};
  *((_QWORD *)a1 + 13) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
  *((_QWORD *)a1 + 22) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CStockPropImpl<CTDCCtl,ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)a1 + 23) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)a1 + 24) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleControlImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 25) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleObjectImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 26) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceActiveObjectImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 27) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IViewObjectExImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 28) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 29) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPersistPropertyBagImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 30) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IRunnableObjectImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 31) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IConnectionPointContainerImpl<CTDCCtl>'};
  *((_QWORD *)a1 + 32) = &ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPropertyNotifySinkCP<CTDCCtl,ATL::CComDynamicUnkArray>'};
  *((_QWORD *)a1 + 35) = &ATL::CComObject<CTDCCtl>::`vftable'{for `CProxyITDCCtlEvents<CTDCCtl>'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v2 + 8LL))(v2);
  return a1;
}

```

## disassembly

```asm
0x18000eec8  push    rbx
0x18000eeca  sub     rsp, 20h
0x18000eece  mov     rbx, rcx
0x18000eed1  call    ??0CTDCCtl@@QEAA@XZ; CTDCCtl::CTDCCtl(void)
0x18000eed6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000eedd  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6BCComControlBase@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CComControlBase'}
0x18000eee4  mov     [rbx], rax
0x18000eee7  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x18000eeee  mov     [rbx+68h], rax
0x18000eef2  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$CStockPropImpl@VCTDCCtl@@UITDCCtl@@$1?IID_ITDCCtl@@3U_GUID@@B$1?LIBID_TDCLib@@3U4@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::CStockPropImpl<CTDCCtl,ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'}
0x18000eef9  mov     [rbx+0B0h], rax
0x18000ef00  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IProvideClassInfo2Impl@$1?CLSID_CTDCCtl@@3U_GUID@@B$1?IID_ITDCCtlEvents@@3U2@B$1?LIBID_TDCLib@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'}
0x18000ef07  mov     [rbx+0B8h], rax
0x18000ef0e  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleControlImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleControlImpl<CTDCCtl>'}
0x18000ef15  mov     [rbx+0C0h], rax
0x18000ef1c  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleObjectImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleObjectImpl<CTDCCtl>'}
0x18000ef23  mov     [rbx+0C8h], rax
0x18000ef2a  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleInPlaceActiveObjectImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceActiveObjectImpl<CTDCCtl>'}
0x18000ef31  mov     [rbx+0D0h], rax
0x18000ef38  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IViewObjectExImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IViewObjectExImpl<CTDCCtl>'}
0x18000ef3f  mov     [rbx+0D8h], rax
0x18000ef46  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IOleInPlaceObjectWindowlessImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>'}
0x18000ef4d  mov     [rbx+0E0h], rax
0x18000ef54  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IPersistPropertyBagImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPersistPropertyBagImpl<CTDCCtl>'}
0x18000ef5b  mov     [rbx+0E8h], rax
0x18000ef62  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IRunnableObjectImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IRunnableObjectImpl<CTDCCtl>'}
0x18000ef69  mov     [rbx+0F0h], rax
0x18000ef70  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IConnectionPointContainerImpl@VCTDCCtl@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IConnectionPointContainerImpl<CTDCCtl>'}
0x18000ef77  mov     [rbx+0F8h], rax
0x18000ef7e  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$IPropertyNotifySinkCP@VCTDCCtl@@VCComDynamicUnkArray@ATL@@@1@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `ATL::IPropertyNotifySinkCP<CTDCCtl,ATL::CComDynamicUnkArray>'}
0x18000ef85  mov     [rbx+100h], rax
0x18000ef8c  lea     rax, ??_7?$CComObject@VCTDCCtl@@@ATL@@6B?$CProxyITDCCtlEvents@VCTDCCtl@@@@@; const ATL::CComObject<CTDCCtl>::`vftable'{for `CProxyITDCCtlEvents<CTDCCtl>'}
0x18000ef93  mov     [rbx+118h], rax
0x18000ef9a  mov     rax, [rcx]
0x18000ef9d  mov     rax, [rax+8]
0x18000efa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efa6  mov     rax, rbx
0x18000efa9  add     rsp, 20h
0x18000efad  pop     rbx
0x18000efae  retn
```
