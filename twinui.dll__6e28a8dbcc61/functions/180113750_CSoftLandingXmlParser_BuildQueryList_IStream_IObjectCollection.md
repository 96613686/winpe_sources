# CSoftLandingXmlParser::BuildQueryList(IStream *,IObjectCollection *)

- ea: `0x180113750`
- end: `0x18011418d`
- name: `?BuildQueryList@CSoftLandingXmlParser@@UEAAJPEAUIStream@@PEAUIObjectCollection@@@Z`
- size: `2621`
- prototype: `__int64 __fastcall(CSoftLandingXmlParser *__hidden this, struct IStream *, struct IObjectCollection *)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b7e8`
- `0x180022c60`
- `0x18003c5e4`
- `0x180054170`
- `0x180113750`
- `0x180114194`
- `0x1801141dc`
- `0x18011423c`
- `0x180114284`
- `0x18013d330`
- `0x18031bafc`
- `0x180323e88`
- `0x18032de04`
- `0x18032def0`
- `0x18032dfb0`
- `0x18032e0ec`
- `0x18032e3dc`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113aeb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113b91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113bbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113be2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c2b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c5f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113cc1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113aeb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113b91`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113bbb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113be2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c2b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c5f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c80`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113c9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180113cc1`
- `XmlLite!CreateXmlReader` at `0x18011380b`
- `XmlLite!CreateXmlReader` at `0x18011380b`

## string_xrefs

- `0x180113825`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180113895`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180113906`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x18011397b`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180113eb1`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180113f24`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x18011404b`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x1801140b8`: `shell\twinui\softlanding\lib\softlandingxmlparser.cpp`
- `0x180113788`: `ParseXML`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CSoftLandingXmlParser::BuildQueryList(
        CSoftLandingXmlParser *this,
        struct IStream *a2,
        struct IObjectCollection *a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // r14d
  int v10; // esi
  int v11; // eax
  _BYTE *v12; // rdi
  int v13; // eax
  unsigned int (*i)(void); // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // r9
  CSoftLandingXmlParser *v18; // rcx
  __int64 (__fastcall *v19)(_BYTE *, GUID *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  void *ppvObject; // [rsp+38h] [rbp-C8h] BYREF
  struct IObjectCollection *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  LPCWCH v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  int v30; // [rsp+5Ch] [rbp-A4h] BYREF
  int v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch] BYREF
  LPCWCH v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h] BYREF
  int v35; // [rsp+78h] [rbp-88h] BYREF
  LPCWCH lpString2; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v37[4]; // [rsp+88h] [rbp-78h] BYREF
  char v38; // [rsp+A8h] [rbp-58h]
  _QWORD v39[42]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v26 = a3;
  wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v39);
  v39[0] = &SoftLandingTelemetry::ParseXML::`vftable';
  SoftLandingTelemetry::ParseXML::StartActivity((SoftLandingTelemetry::ParseXML *)v39);
  v24 = -2147467259;
  ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
  v37[1] = &v24;
  v37[2] = &v26;
  v37[3] = v39;
  v38 = 1;
  ppvObject = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
  v4 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v5 = v4;
  v24 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v6 = (*(__int64 (__fastcall **)(void *, struct IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, a2);
  v5 = v6;
  v24 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v6,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v7 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  v5 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v8 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 6, 200);
  v5 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v8,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v9 = 0;
  v31 = 0;
  v10 = 0;
  v27 = 0;
  do
  {
    while ( 1 )
    {
LABEL_18:
      if ( v24 < 0 || (*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 200LL))(ppvObject) )
        goto LABEL_105;
      v35 = 0;
      v11 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v35);
      v24 = v11;
      if ( v11 < 0 || v11 == 1 || !v35 )
      {
        if ( v9 > 0 && !v10 )
          goto LABEL_106;
        SoftLandingTelemetry::MismatchedElements<int &,int &>(&v31, &v27);
LABEL_105:
        if ( v24 == 1 )
LABEL_106:
          v24 = 0;
        v5 = v24;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
        if ( v24 < 0 )
          ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
        goto LABEL_109;
      }
      v30 = 0;
      if ( v35 == 1 )
        break;
      if ( v35 == 15 )
      {
        v27 = --v10;
        if ( v10 < 0 )
        {
          SoftLandingTelemetry::MismatchedElements<int &,int &>(&v31, &v27);
          v5 = -1072894419;
          v24 = -1072894419;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
          if ( v24 < 0 )
            ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
          goto LABEL_109;
        }
      }
    }
    v31 = ++v9;
    if ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 160LL))(ppvObject) )
      v27 = ++v10;
    lpString2 = 0;
  }
  while ( (*(int (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 112LL))(ppvObject, &lpString2, &v30) < 0 );
  Microsoft::WRL::Details::Make<CSoftLandingQueryEntry,>(v37);
  v12 = (_BYTE *)v37[0];
  if ( !v37[0] )
  {
    v5 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)0x8007000ELL,
      bIgnoreCase);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  v29 = 0;
  v13 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 192LL))(ppvObject, &v29);
  v5 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    if ( v12 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  if ( CompareStringOrdinal(L"Root", -1, lpString2, -1, 1) == 2 )
  {
    if ( v29 )
    {
      SoftLandingTelemetry::MultipleRootElements();
      v5 = -1072894419;
      v24 = -1072894419;
      if ( v12 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
      if ( v24 < 0 )
        ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
      goto LABEL_109;
    }
    v12[16] = 1;
  }
  else if ( !v29 )
  {
    SoftLandingTelemetry::NoRootElement();
    v5 = -1072894419;
    v24 = -1072894419;
    if ( v12 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    goto LABEL_109;
  }
  for ( i = *(unsigned int (**)(void))(*(_QWORD *)ppvObject + 64LL);
        !i();
        i = *(unsigned int (**)(void))(*(_QWORD *)ppvObject + 72LL) )
  {
    v28 = 0;
    v33 = 0;
    if ( (*(int (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 112LL))(ppvObject, &v28, &v30) >= 0
      && (*(int (__fastcall **)(void *, LPCWCH *, int *))(*(_QWORD *)ppvObject + 128LL))(ppvObject, &v33, &v30) >= 0 )
    {
      if ( CompareStringOrdinal(L"Id", -1, v28, -1, 1) == 2 )
      {
        v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v12 + 40);
LABEL_45:
        _AllocString<CTCoAllocPolicy>(v16, v15, v33, v17);
        continue;
      }
      if ( CompareStringOrdinal(L"Class", -1, v28, -1, 1) == 2 )
      {
        v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v12 + 32);
        goto LABEL_45;
      }
      if ( CompareStringOrdinal(L"Type", -1, v28, -1, 1) == 2 )
      {
        v32 = -1;
        if ( CSoftLandingXmlParser::_UIAControlStringToValue(v18, v33, &v32) >= 0 )
          *((_DWORD *)v12 + 5) = v32;
      }
      else
      {
        if ( CompareStringOrdinal(L"Name", -1, v28, -1, 1) == 2 )
        {
          v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))(v12 + 24);
          goto LABEL_45;
        }
        if ( CompareStringOrdinal(L"IgnoreCase", -1, v28, -1, 1) == 2 )
        {
          v12[17] = CompareStringOrdinal(L"true", -1, v33, -1, 1) == 2;
        }
        else
        {
          if ( CompareStringOrdinal(L"UseRegExForId", -1, v28, -1, 1) != 2 )
          {
            SoftLandingTelemetry::UnknownAttribute<unsigned short const * &>(&v28);
            v5 = -1072894419;
            v24 = -1072894419;
            if ( v12 )
              (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
            if ( v24 < 0 )
              ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
            goto LABEL_109;
          }
          v12[18] = CompareStringOrdinal(L"true", -1, v33, -1, 1) == 2;
        }
      }
    }
  }
  if ( v24 < 0 || (*(unsigned __int8 (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 24LL))(v12) )
  {
    SoftLandingTelemetry::EmptyQuery();
    v5 = -1072894419;
    v24 = -1072894419;
    if ( v12 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
    if ( v24 < 0 )
      ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
  }
  else
  {
    v34 = 0;
    v19 = **(__int64 (__fastcall ***)(_BYTE *, GUID *, __int64 *))v12;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
    v20 = v19(v12, &GUID_00000000_0000_0000_c000_000000000046, &v34);
    v5 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
        (const char *)(unsigned int)v20,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      if ( v12 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
      if ( v24 < 0 )
        ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    }
    else
    {
      v21 = ((__int64 (__fastcall *)(struct IObjectCollection *, __int64))v26->lpVtbl->AddObject)(v26, v34);
      v5 = v21;
      if ( v21 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
        if ( v12 )
        {
          v37[0] = 0;
          (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        goto LABEL_18;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\softlandingxmlparser.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
      if ( v12 )
        (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v12 + 16LL))(v12);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvObject);
      if ( v24 < 0 )
        ((void (__fastcall *)(struct IObjectCollection *))v26->lpVtbl->Clear)(v26);
    }
  }
LABEL_109:
  wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v39);
  SoftLandingTelemetry::ParseXML::~ParseXML((SoftLandingTelemetry::ParseXML *)v39);
  return v5;
}

```

## disassembly

```asm
0x180113750  mov     [rsp-8+arg_0], rbx
0x180113755  push    rbp
0x180113756  push    rsi
0x180113757  push    rdi
0x180113758  push    r12
0x18011375a  push    r13
0x18011375c  push    r14
0x18011375e  push    r15
0x180113760  lea     rbp, [rsp-110h]
0x180113768  sub     rsp, 210h
0x18011376f  mov     rax, cs:__security_cookie
0x180113776  xor     rax, rsp
0x180113779  mov     [rbp+140h+var_40], rax
0x180113780  mov     rdi, rdx
0x180113783  mov     [rsp+240h+var_200], r8
0x180113788  lea     rdx, aParsexml; "ParseXML"
0x18011378f  lea     rcx, [rbp+140h+var_190]; struct wil::details::IFailureCallback *
0x180113793  call    ??0?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180113798  lea     rax, ??_7ParseXML@SoftLandingTelemetry@@6B@; const SoftLandingTelemetry::ParseXML::`vftable'
0x18011379f  mov     [rbp+140h+var_190], rax
0x1801137a3  lea     rcx, [rbp+140h+var_190]; this
0x1801137a7  call    ?StartActivity@ParseXML@SoftLandingTelemetry@@QEAAXXZ; SoftLandingTelemetry::ParseXML::StartActivity(void)
0x1801137ac  nop
0x1801137ad  mov     [rsp+240h+var_210], 80004005h
0x1801137b5  mov     rcx, [rsp+240h+var_200]
0x1801137ba  mov     rax, [rcx]
0x1801137bd  mov     rax, [rax+40h]
0x1801137c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801137c6  lea     rax, [rsp+240h+var_210]
0x1801137cb  mov     [rbp+140h+var_1B0], rax
0x1801137cf  lea     rax, [rsp+240h+var_200]
0x1801137d4  mov     [rbp+140h+var_1A8], rax
0x1801137d8  lea     rax, [rbp+140h+var_190]
0x1801137dc  mov     [rbp+140h+var_1A0], rax
0x1801137e0  mov     r13d, 1
0x1801137e6  mov     [rbp+140h+var_198], r13b
0x1801137ea  xor     r15d, r15d
0x1801137ed  mov     [rsp+240h+ppvObject], r15
0x1801137f2  lea     rcx, [rsp+240h+ppvObject]
0x1801137f7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801137fc  xor     r8d, r8d; pMalloc
0x1801137ff  lea     rdx, [rsp+240h+ppvObject]; ppvObject
0x180113804  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18011380b  call    cs:__imp_CreateXmlReader
0x180113811  mov     ebx, eax
0x180113813  mov     [rsp+240h+var_210], eax
0x180113817  test    eax, eax
0x180113819  jns     short loc_18011386D
0x18011381b  mov     rcx, [rbp+148h]; this
0x180113822  mov     r9d, eax; char *
0x180113825  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x18011382c  lea     edx, [r13+17h]; void *
0x180113830  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113835  nop
0x180113836  lea     rcx, [rsp+240h+ppvObject]
0x18011383b  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180113840  nop
0x180113841  mov     edx, [rsp+240h+var_210]
0x180113845  test    edx, edx
0x180113847  jns     short loc_18011385E
0x180113849  mov     rcx, [rsp+240h+var_200]
0x18011384e  mov     rax, [rcx]
0x180113851  mov     rax, [rax+40h]
0x180113855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011385a  mov     edx, [rsp+240h+var_210]
0x18011385e  lea     rcx, [rbp+140h+var_190]
0x180113862  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180113867  nop
0x180113868  jmp     loc_180114158
0x18011386d  mov     rcx, [rsp+240h+ppvObject]
0x180113872  mov     rax, [rcx]
0x180113875  mov     rdx, rdi
0x180113878  mov     rax, [rax+18h]
0x18011387c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113881  mov     ebx, eax
0x180113883  mov     [rsp+240h+var_210], eax
0x180113887  test    eax, eax
0x180113889  jns     short loc_1801138DE
0x18011388b  mov     rcx, [rbp+148h]; this
0x180113892  mov     r9d, eax; char *
0x180113895  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x18011389c  mov     edx, 19h; void *
0x1801138a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801138a6  nop
0x1801138a7  lea     rcx, [rsp+240h+ppvObject]
0x1801138ac  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801138b1  nop
0x1801138b2  mov     edx, [rsp+240h+var_210]
0x1801138b6  test    edx, edx
0x1801138b8  jns     short loc_1801138CF
0x1801138ba  mov     rcx, [rsp+240h+var_200]
0x1801138bf  mov     rax, [rcx]
0x1801138c2  mov     rax, [rax+40h]
0x1801138c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801138cb  mov     edx, [rsp+240h+var_210]
0x1801138cf  lea     rcx, [rbp+140h+var_190]
0x1801138d3  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1801138d8  nop
0x1801138d9  jmp     loc_180114158
0x1801138de  mov     rcx, [rsp+240h+ppvObject]
0x1801138e3  mov     rax, [rcx]
0x1801138e6  xor     r8d, r8d
0x1801138e9  lea     edx, [r8+4]
0x1801138ed  mov     rax, [rax+28h]
0x1801138f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801138f6  mov     ebx, eax
0x1801138f8  test    eax, eax
0x1801138fa  jns     short loc_18011394F
0x1801138fc  mov     rcx, [rbp+148h]; this
0x180113903  mov     r9d, eax; char *
0x180113906  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x18011390d  mov     edx, 1Ah; void *
0x180113912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113917  nop
0x180113918  lea     rcx, [rsp+240h+ppvObject]
0x18011391d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180113922  nop
0x180113923  mov     edx, [rsp+240h+var_210]
0x180113927  test    edx, edx
0x180113929  jns     short loc_180113940
0x18011392b  mov     rcx, [rsp+240h+var_200]
0x180113930  mov     rax, [rcx]
0x180113933  mov     rax, [rax+40h]
0x180113937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011393c  mov     edx, [rsp+240h+var_210]
0x180113940  lea     rcx, [rbp+140h+var_190]
0x180113944  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180113949  nop
0x18011394a  jmp     loc_180114158
0x18011394f  mov     rcx, [rsp+240h+ppvObject]
0x180113954  mov     rax, [rcx]
0x180113957  mov     edx, 6
0x18011395c  mov     r8d, 0C8h
0x180113962  mov     rax, [rax+28h]
0x180113966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011396b  mov     ebx, eax
0x18011396d  test    eax, eax
0x18011396f  jns     short loc_1801139C4
0x180113971  mov     rcx, [rbp+148h]; this
0x180113978  mov     r9d, eax; char *
0x18011397b  lea     r8, aShellTwinuiSof_5; "shell\\twinui\\softlanding\\lib\\softla"...
0x180113982  mov     edx, 1Bh; void *
0x180113987  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011398c  nop
0x18011398d  lea     rcx, [rsp+240h+ppvObject]
0x180113992  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180113997  nop
0x180113998  mov     edx, [rsp+240h+var_210]
0x18011399c  test    edx, edx
0x18011399e  jns     short loc_1801139B5
0x1801139a0  mov     rcx, [rsp+240h+var_200]
0x1801139a5  mov     rax, [rcx]
0x1801139a8  mov     rax, [rax+40h]
0x1801139ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801139b1  mov     edx, [rsp+240h+var_210]
0x1801139b5  lea     rcx, [rbp+140h+var_190]
0x1801139b9  call    ?Stop@?$ActivityBase@VSoftLandingLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<SoftLandingLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1801139be  nop
0x1801139bf  jmp     loc_180114158
0x1801139c4  mov     r14d, r15d
0x1801139c7  mov     [rsp+240h+var_1E0], r15d
0x1801139cc  mov     esi, r15d
0x1801139cf  mov     [rsp+240h+var_1F8], r15d
0x1801139d4  or      r12d, 0FFFFFFFFh
0x1801139d8  cmp     [rsp+240h+var_210], r15d
0x1801139dd  jl      loc_180114116
0x1801139e3  mov     rcx, [rsp+240h+ppvObject]
0x1801139e8  mov     rax, [rcx]
0x1801139eb  mov     rax, [rax+0C8h]
0x1801139f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801139f7  test    eax, eax
0x1801139f9  jnz     loc_180114116
0x1801139ff  mov     [rsp+240h+var_1C8], r15d
0x180113a04  mov     rcx, [rsp+240h+ppvObject]
0x180113a09  mov     rax, [rcx]
0x180113a0c  lea     rdx, [rsp+240h+var_1C8]
0x180113a11  mov     rax, [rax+30h]
0x180113a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113a1a  mov     [rsp+240h+var_210], eax
0x180113a1e  test    eax, eax
0x180113a20  js      loc_1801140FE
0x180113a26  cmp     eax, r13d
0x180113a29  jz      loc_1801140FE
0x180113a2f  mov     eax, [rsp+240h+var_1C8]
0x180113a33  test    eax, eax
0x180113a35  jz      loc_1801140FE
0x180113a3b  mov     [rsp+240h+var_1E4], r15d
0x180113a40  cmp     eax, r13d
0x180113a43  jnz     loc_180113D89
0x180113a49  add     r14d, r13d
0x180113a4c  mov     [rsp+240h+var_1E0], r14d
0x180113a51  mov     rcx, [rsp+240h+ppvObject]
0x180113a56  mov     rax, [rcx]
0x180113a59  mov     rax, [rax+0A0h]
0x180113a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113a65  test    eax, eax
0x180113a67  jnz     short loc_180113A70
0x180113a69  add     esi, r13d
0x180113a6c  mov     [rsp+240h+var_1F8], esi
0x180113a70  mov     [rbp+140h+lpString2], r15
0x180113a74  mov     rcx, [rsp+240h+ppvObject]
0x180113a79  mov     rax, [rcx]
0x180113a7c  lea     r8, [rsp+240h+var_1E4]
0x180113a81  lea     rdx, [rbp+140h+lpString2]
0x180113a85  mov     rax, [rax+70h]
0x180113a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113a8e  test    eax, eax
0x180113a90  js      loc_1801139D8
0x180113a96  lea     rcx, [rbp+140h+var_1B8]
0x180113a9a  call    ??$Make@VCSoftLandingQueryEntry@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCSoftLandingQueryEntry@@@12@XZ; Microsoft::WRL::Details::Make<CSoftLandingQueryEntry,>(void)
0x180113a9f  nop
0x180113aa0  mov     rdi, [rbp+140h+var_1B8]
0x180113aa4  test    rdi, rdi
0x180113aa7  jz      loc_1801140A9
0x180113aad  mov     [rsp+240h+var_1E8], r15d
0x180113ab2  mov     rcx, [rsp+240h+ppvObject]
0x180113ab7  mov     rax, [rcx]
0x180113aba  lea     rdx, [rsp+240h+var_1E8]
0x180113abf  mov     rax, [rax+0C0h]
0x180113ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113acb  mov     ebx, eax
0x180113acd  test    eax, eax
0x180113acf  js      loc_180114041
0x180113ad5  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x180113ada  mov     r9d, r12d; cchCount2
0x180113add  mov     r8, [rbp+140h+lpString2]; lpString2
0x180113ae1  mov     edx, r12d; cchCount1
0x180113ae4  lea     rcx, String1; "Root"
0x180113aeb  call    cs:__imp_CompareStringOrdinal
0x180113af1  mov     ebx, 2
0x180113af6  cmp     eax, ebx
0x180113af8  jnz     short loc_180113B0B
0x180113afa  cmp     [rsp+240h+var_1E8], r15d
0x180113aff  ja      loc_180113DEE
0x180113b05  mov     [rdi+10h], r13b
0x180113b09  jmp     short loc_180113B16
0x180113b0b  cmp     [rsp+240h+var_1E8], r15d
0x180113b10  jz      loc_180113FE7
0x180113b16  mov     rcx, [rsp+240h+ppvObject]
0x180113b1b  mov     rax, [rcx]
0x180113b1e  mov     rax, [rax+40h]
0x180113b22  jmp     loc_180113CDB
0x180113b27  mov     [rsp+240h+var_1F0], r15
0x180113b2c  mov     [rsp+240h+var_1D8], r15
0x180113b31  mov     rcx, [rsp+240h+ppvObject]
0x180113b36  mov     rax, [rcx]
0x180113b39  lea     r8, [rsp+240h+var_1E4]
0x180113b3e  lea     rdx, [rsp+240h+var_1F0]
0x180113b43  mov     rax, [rax+70h]
0x180113b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113b4c  test    eax, eax
0x180113b4e  js      loc_180113CCF
0x180113b54  mov     rcx, [rsp+240h+ppvObject]
0x180113b59  mov     rax, [rcx]
0x180113b5c  lea     r8, [rsp+240h+var_1E4]
0x180113b61  lea     rdx, [rsp+240h+var_1D8]
0x180113b66  mov     rax, [rax+80h]
0x180113b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113b72  test    eax, eax
0x180113b74  js      loc_180113CCF
0x180113b7a  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x180113b7f  mov     r9d, r12d; cchCount2
0x180113b82  mov     r8, [rsp+240h+var_1F0]; lpString2
0x180113b87  mov     edx, r12d; cchCount1
0x180113b8a  lea     rcx, aId; "Id"
0x180113b91  call    cs:__imp_CompareStringOrdinal
0x180113b97  cmp     eax, ebx
0x180113b99  jnz     short loc_180113BA4
0x180113b9b  lea     r9, [rdi+28h]
0x180113b9f  jmp     loc_180113C39
0x180113ba4  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x180113ba9  mov     r9d, r12d; cchCount2
0x180113bac  mov     r8, [rsp+240h+var_1F0]; lpString2
0x180113bb1  mov     edx, r12d; cchCount1
0x180113bb4  lea     rcx, aClass; "Class"
0x180113bbb  call    cs:__imp_CompareStringOrdinal
0x180113bc1  cmp     eax, ebx
0x180113bc3  jnz     short loc_180113BCB
0x180113bc5  lea     r9, [rdi+20h]
0x180113bc9  jmp     short loc_180113C39
0x180113bcb  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x180113bd0  mov     r9d, r12d; cchCount2
0x180113bd3  mov     r8, [rsp+240h+var_1F0]; lpString2
0x180113bd8  mov     edx, r12d; cchCount1
0x180113bdb  lea     rcx, aType; "Type"
0x180113be2  call    cs:__imp_CompareStringOrdinal
0x180113be8  cmp     eax, ebx
0x180113bea  jnz     short loc_180113C14
0x180113bec  mov     [rsp+240h+var_1DC], r12d
0x180113bf1  lea     r8, [rsp+240h+var_1DC]; int *
0x180113bf6  mov     rdx, [rsp+240h+var_1D8]; unsigned __int16 *
0x180113bfb  call    ?_UIAControlStringToValue@CSoftLandingXmlParser@@AEAAJPEBGPEAH@Z; CSoftLandingXmlParser::_UIAControlStringToValue(ushort const *,int *)
0x180113c00  test    eax, eax
0x180113c02  js      loc_180113CCF
0x180113c08  mov     eax, [rsp+240h+var_1DC]
0x180113c0c  mov     [rdi+14h], eax
0x180113c0f  jmp     loc_180113CCF
0x180113c14  mov     [rsp+240h+bIgnoreCase], r13d; bIgnoreCase
0x180113c19  mov     r9d, r12d; cchCount2
0x180113c1c  mov     r8, [rsp+240h+var_1F0]; lpString2
  ... truncated ...
```
