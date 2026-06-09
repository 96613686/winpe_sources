# CTDCCtl::CTDCCtl(void)

- ea: `0x180002364`
- end: `0x18000269d`
- name: `??0CTDCCtl@@QEAA@XZ`
- size: `825`
- prototype: `CTDCCtl *__fastcall(CTDCCtl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000eec8`

## callees

- `0x1800011b8`
- `0x180002364`
- `0x180003b70`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180002673`
- `ole32!CoCreateInstance` at `0x180002673`
- `OLEAUT32!__imp_SysAllocString` at `0x180002528`
- `OLEAUT32!__imp_SysAllocString` at `0x18000255a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000258c`
- `OLEAUT32!__imp_SysAllocString` at `0x180002528`
- `OLEAUT32!__imp_SysAllocString` at `0x18000255a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000258c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000251b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002551`
- `OLEAUT32!__imp_SysFreeString` at `0x180002583`
- `OLEAUT32!__imp_SysFreeString` at `0x18000251b`
- `OLEAUT32!__imp_SysFreeString` at `0x180002551`
- `OLEAUT32!__imp_SysFreeString` at `0x180002583`
- `USER32!DefWindowProcA` at `0x1800023b7`

## pseudocode

```c
CTDCCtl *__fastcall CTDCCtl::CTDCCtl(CTDCCtl *this)
{
  BSTR v2; // rax
  OLECHAR *v3; // rcx
  BSTR v4; // rax
  OLECHAR *v5; // rcx
  BSTR v6; // rax
  _DWORD *v7; // rax
  CTDCCtl *result; // rax

  *((_DWORD *)this + 76) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 25) &= 0xFFFFC000;
  *((_DWORD *)this + 16) = 5080;
  *((_DWORD *)this + 17) = 5080;
  *((_QWORD *)this + 7) = *((_QWORD *)this + 8);
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = (char *)this + 112;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 21) = DefWindowProcA;
  *(_QWORD *)this = &CTDCCtl::`vftable'{for `ATL::CComControlBase'};
  *((_QWORD *)this + 13) = &CTDCCtl::`vftable'{for `ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'};
  *((_QWORD *)this + 22) = &CTDCCtl::`vftable'{for `ATL::CStockPropImpl<CTDCCtl,ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 23) = &CTDCCtl::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'};
  *((_QWORD *)this + 24) = &CTDCCtl::`vftable'{for `ATL::IOleControlImpl<CTDCCtl>'};
  *((_QWORD *)this + 25) = &CTDCCtl::`vftable'{for `ATL::IOleObjectImpl<CTDCCtl>'};
  *((_QWORD *)this + 26) = &CTDCCtl::`vftable'{for `ATL::IOleInPlaceActiveObjectImpl<CTDCCtl>'};
  *((_QWORD *)this + 27) = &CTDCCtl::`vftable'{for `ATL::IViewObjectExImpl<CTDCCtl>'};
  *((_QWORD *)this + 28) = &CTDCCtl::`vftable'{for `ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>'};
  *((_QWORD *)this + 29) = &CTDCCtl::`vftable'{for `ATL::IPersistPropertyBagImpl<CTDCCtl>'};
  *((_QWORD *)this + 30) = &CTDCCtl::`vftable'{for `ATL::IRunnableObjectImpl<CTDCCtl>'};
  *((_QWORD *)this + 31) = &CTDCCtl::`vftable'{for `ATL::IConnectionPointContainerImpl<CTDCCtl>'};
  *((_QWORD *)this + 32) = &CTDCCtl::`vftable'{for `ATL::IPropertyNotifySinkCP<CTDCCtl,ATL::CComDynamicUnkArray>'};
  *((_QWORD *)this + 35) = &CTDCCtl::`vftable'{for `CProxyITDCCtlEvents<CTDCCtl>'};
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_DWORD *)this + 40) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_DWORD *)this + 88) = 0;
  *((_DWORD *)this + 68) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_DWORD *)this + 74) = 0;
  *((_QWORD *)this + 36) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 14) = 0;
  SysFreeString(0);
  v2 = SysAllocString(L",");
  *((_QWORD *)this + 45) = v2;
  if ( !v2 )
    goto LABEL_10;
  v3 = (OLECHAR *)*((_QWORD *)this + 46);
  if ( L"\n" != v3 )
  {
    SysFreeString(v3);
    v4 = SysAllocString(L"\n");
    *((_QWORD *)this + 46) = v4;
    if ( !v4 )
      goto LABEL_10;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 47);
  if ( L"\"" != v5 )
  {
    SysFreeString(v5);
    v6 = SysAllocString(L"\"");
    *((_QWORD *)this + 47) = v6;
    if ( !v6 )
LABEL_10:
      ATL::AtlThrowImpl(-2147024882);
  }
  *((_DWORD *)this + 98) = 0;
  *((_DWORD *)this + 102) = 1;
  *((_DWORD *)this + 124) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 71) = 0;
  v7 = operator new(0x40u);
  if ( v7 )
  {
    v7[4] = 1;
    *(_QWORD *)v7 = &CEventBroker::`vftable';
    *((_QWORD *)v7 + 5) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 1) = 0;
    *((_QWORD *)v7 + 7) = this;
    v7[12] = 4;
  }
  else
  {
    v7 = 0;
  }
  *((_QWORD *)this + 70) = v7;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 66) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 106) = 0;
  *((_BYTE *)this + 468) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_DWORD *)this + 125) = 1;
  *((_BYTE *)this + 504) = 0;
  *((_DWORD *)this + 127) = 0;
  *((_DWORD *)this + 110) = 0;
  CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage, (LPVOID *)this + 66);
  result = this;
  *((_DWORD *)this + 116) = 0;
  return result;
}

```

## disassembly

```asm
0x180002364  mov     [rsp+arg_0], rbx
0x180002369  mov     [rsp+arg_8], rsi
0x18000236e  push    rdi
0x18000236f  sub     rsp, 30h
0x180002373  xor     edi, edi
0x180002375  lea     rdx, [rcx+70h]
0x180002379  mov     [rcx+130h], edi
0x18000237f  mov     eax, 13D8h
0x180002384  mov     [rcx+8], rdi
0x180002388  xorps   xmm0, xmm0
0x18000238b  mov     [rcx+10h], rdi
0x18000238f  mov     rbx, rcx
0x180002392  mov     [rcx+18h], rdi
0x180002396  mov     [rcx+20h], rdi
0x18000239a  mov     [rcx+28h], rdi
0x18000239e  mov     [rcx+30h], rdi
0x1800023a2  and     dword ptr [rcx+64h], 0FFFFC000h
0x1800023a9  mov     [rcx+40h], eax
0x1800023ac  mov     [rcx+44h], eax
0x1800023af  mov     rax, [rcx+40h]
0x1800023b3  mov     [rcx+38h], rax
0x1800023b7  mov     rax, cs:__imp_DefWindowProcA
0x1800023be  movdqu  xmmword ptr [rcx+48h], xmm0
0x1800023c3  mov     [rcx+58h], rdx
0x1800023c7  mov     [rcx+60h], edi
0x1800023ca  mov     [rcx+0A8h], rax
0x1800023d1  lea     rax, ??_7CTDCCtl@@6BCComControlBase@ATL@@@; const CTDCCtl::`vftable'{for `ATL::CComControlBase'}
0x1800023d8  mov     [rcx], rax
0x1800023db  lea     rax, ??_7CTDCCtl@@6B?$CWindowImpl@VCTDCCtl@@VCWindow@ATL@@V?$CWinTraits@$0FGAAAAAA@$0A@@3@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::CWindowImpl<CTDCCtl,ATL::CWindow,ATL::CWinTraits<1442840576,0>>'}
0x1800023e2  mov     [rcx+68h], rax
0x1800023e6  lea     rax, ??_7CTDCCtl@@6B?$CStockPropImpl@VCTDCCtl@@UITDCCtl@@$1?IID_ITDCCtl@@3U_GUID@@B$1?LIBID_TDCLib@@3U4@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::CStockPropImpl<CTDCCtl,ITDCCtl,&_GUID const IID_ITDCCtl,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'}
0x1800023ed  mov     [rcx+0B0h], rax
0x1800023f4  lea     rax, ??_7CTDCCtl@@6B?$IProvideClassInfo2Impl@$1?CLSID_CTDCCtl@@3U_GUID@@B$1?IID_ITDCCtlEvents@@3U2@B$1?LIBID_TDCLib@@3U2@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IProvideClassInfo2Impl<&_GUID const CLSID_CTDCCtl,&_GUID const IID_ITDCCtlEvents,&_GUID const LIBID_TDCLib,1,0,ATL::CComTypeInfoHolder>'}
0x1800023fb  mov     [rcx+0B8h], rax
0x180002402  lea     rax, ??_7CTDCCtl@@6B?$IOleControlImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IOleControlImpl<CTDCCtl>'}
0x180002409  mov     [rcx+0C0h], rax
0x180002410  lea     rax, ??_7CTDCCtl@@6B?$IOleObjectImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IOleObjectImpl<CTDCCtl>'}
0x180002417  mov     [rcx+0C8h], rax
0x18000241e  lea     rax, ??_7CTDCCtl@@6B?$IOleInPlaceActiveObjectImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IOleInPlaceActiveObjectImpl<CTDCCtl>'}
0x180002425  mov     [rcx+0D0h], rax
0x18000242c  lea     rax, ??_7CTDCCtl@@6B?$IViewObjectExImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IViewObjectExImpl<CTDCCtl>'}
0x180002433  mov     [rcx+0D8h], rax
0x18000243a  lea     rax, ??_7CTDCCtl@@6B?$IOleInPlaceObjectWindowlessImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IOleInPlaceObjectWindowlessImpl<CTDCCtl>'}
0x180002441  mov     [rcx+0E0h], rax
0x180002448  lea     rax, ??_7CTDCCtl@@6B?$IPersistPropertyBagImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IPersistPropertyBagImpl<CTDCCtl>'}
0x18000244f  mov     [rcx+0E8h], rax
0x180002456  lea     rax, ??_7CTDCCtl@@6B?$IRunnableObjectImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IRunnableObjectImpl<CTDCCtl>'}
0x18000245d  mov     [rcx+0F0h], rax
0x180002464  lea     rax, ??_7CTDCCtl@@6B?$IConnectionPointContainerImpl@VCTDCCtl@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IConnectionPointContainerImpl<CTDCCtl>'}
0x18000246b  mov     [rcx+0F8h], rax
0x180002472  lea     rax, ??_7CTDCCtl@@6B?$IPropertyNotifySinkCP@VCTDCCtl@@VCComDynamicUnkArray@ATL@@@ATL@@@; const CTDCCtl::`vftable'{for `ATL::IPropertyNotifySinkCP<CTDCCtl,ATL::CComDynamicUnkArray>'}
0x180002479  mov     [rcx+100h], rax
0x180002480  lea     rax, ??_7CTDCCtl@@6B?$CProxyITDCCtlEvents@VCTDCCtl@@@@@; const CTDCCtl::`vftable'{for `CProxyITDCCtlEvents<CTDCCtl>'}
0x180002487  mov     [rcx+118h], rax
0x18000248e  mov     [rcx+90h], rdi
0x180002495  mov     [rcx+98h], rdi
0x18000249c  mov     [rcx+0A0h], edi
0x1800024a2  mov     [rcx+158h], rdi
0x1800024a9  mov     [rcx+160h], edi
0x1800024af  mov     [rcx+110h], edi
0x1800024b5  mov     [rcx+108h], rdi
0x1800024bc  mov     [rcx+128h], edi
0x1800024c2  mov     [rcx+120h], rdi
0x1800024c9  mov     [rcx+168h], rdi
0x1800024d0  mov     [rcx+170h], rdi
0x1800024d7  mov     [rcx+178h], rdi
0x1800024de  mov     [rcx+180h], rdi
0x1800024e5  mov     [rcx+190h], rdi
0x1800024ec  mov     [rcx+1A0h], rdi
0x1800024f3  mov     [rcx+1B0h], rdi
0x1800024fa  mov     [rcx+1C0h], rdi
0x180002501  mov     [rcx+1C8h], rdi
0x180002508  mov     [rcx+1E0h], rdi
0x18000250f  mov     [rcx+1E8h], rdi
0x180002516  xor     ecx, ecx; bstrString
0x180002518  mov     [rdx], rdi
0x18000251b  call    cs:__imp_SysFreeString
0x180002521  lea     rcx, psz; ","
0x180002528  call    cs:__imp_SysAllocString
0x18000252e  mov     [rbx+168h], rax
0x180002535  test    rax, rax
0x180002538  jz      loc_180002692
0x18000253e  mov     rcx, [rbx+170h]; bstrString
0x180002545  lea     rsi, asc_180018434; "\n"
0x18000254c  cmp     rsi, rcx
0x18000254f  jz      short loc_180002570
0x180002551  call    cs:__imp_SysFreeString
0x180002557  mov     rcx, rsi; psz
0x18000255a  call    cs:__imp_SysAllocString
0x180002560  mov     [rbx+170h], rax
0x180002567  test    rax, rax
0x18000256a  jz      loc_180002692
0x180002570  mov     rcx, [rbx+178h]; bstrString
0x180002577  lea     rsi, asc_180018438; "\""
0x18000257e  cmp     rsi, rcx
0x180002581  jz      short loc_1800025A2
0x180002583  call    cs:__imp_SysFreeString
0x180002589  mov     rcx, rsi; psz
0x18000258c  call    cs:__imp_SysAllocString
0x180002592  mov     [rbx+178h], rax
0x180002599  test    rax, rax
0x18000259c  jz      loc_180002692
0x1800025a2  mov     esi, 1
0x1800025a7  mov     [rbx+188h], edi
0x1800025ad  mov     [rbx+198h], esi
0x1800025b3  mov     [rbx+1F0h], edi
0x1800025b9  mov     [rbx+200h], rdi
0x1800025c0  lea     ecx, [rsi+3Fh]; Size
0x1800025c3  mov     [rbx+208h], rdi
0x1800025ca  mov     [rbx+238h], rdi
0x1800025d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800025d6  test    rax, rax
0x1800025d9  jz      short loc_180002605
0x1800025db  lea     rcx, ??_7CEventBroker@@6B@; const CEventBroker::`vftable'
0x1800025e2  mov     [rax+10h], esi
0x1800025e5  mov     [rax], rcx
0x1800025e8  mov     [rax+28h], rdi
0x1800025ec  mov     [rax+20h], rdi
0x1800025f0  mov     [rax+18h], rdi
0x1800025f4  mov     [rax+8], rdi
0x1800025f8  mov     [rax+38h], rbx
0x1800025fc  mov     dword ptr [rax+30h], 4
0x180002603  jmp     short loc_180002608
0x180002605  mov     rax, rdi
0x180002608  mov     [rbx+230h], rax
0x18000260f  lea     r9, IID_IMultiLanguage; riid
0x180002616  lea     rax, [rbx+210h]
0x18000261d  mov     [rbx+228h], rdi
0x180002624  mov     r8d, esi; dwClsContext
0x180002627  mov     [rax], rdi
0x18000262a  xor     edx, edx; pUnkOuter
0x18000262c  mov     [rsp+38h+ppv], rax; ppv
0x180002631  lea     rcx, CLSID_CMultiLanguage; rclsid
0x180002638  mov     [rbx+220h], rdi
0x18000263f  mov     [rbx+240h], rdi
0x180002646  mov     [rbx+1A8h], edi
0x18000264c  mov     [rbx+1D4h], dil
0x180002653  mov     [rbx+1D8h], rdi
0x18000265a  mov     [rbx+1F4h], esi
0x180002660  mov     [rbx+1F8h], dil
0x180002667  mov     [rbx+1FCh], edi
0x18000266d  mov     [rbx+1B8h], edi
0x180002673  call    cs:__imp_CoCreateInstance
0x180002679  mov     rsi, [rsp+38h+arg_8]
0x18000267e  mov     rax, rbx
0x180002681  mov     [rbx+1D0h], edi
0x180002687  mov     rbx, [rsp+38h+arg_0]
0x18000268c  add     rsp, 30h
0x180002690  pop     rdi
0x180002691  retn
0x180002692  mov     ecx, 8007000Eh; int
0x180002697  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
