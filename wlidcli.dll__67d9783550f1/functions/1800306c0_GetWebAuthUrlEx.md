# GetWebAuthUrlEx

- ea: `0x1800306c0`
- end: `0x18003123c`
- name: `GetWebAuthUrlEx`
- size: `2940`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800306a0`
- `0x1800323b0`

## callees

- `0x180003298`
- `0x18000a914`
- `0x18000af14`
- `0x18000b0bc`
- `0x18000b1d8`
- `0x18000ba8c`
- `0x18000bdf0`
- `0x18000c354`
- `0x18000c538`
- `0x18000cb6c`
- `0x18000cc9c`
- `0x1800114f8`
- `0x180012848`
- `0x18001d378`
- `0x18002126c`
- `0x180023694`
- `0x180025cfc`
- `0x180026130`
- `0x180026474`
- `0x18002932c`
- `0x180029788`
- `0x1800306c0`
- `0x18004bf2c`
- `0x18004c66c`
- `0x180052ba0`
- `0x180052cf4`
- `0x180052d2c`
- `0x180052e48`
- `0x1800530e4`
- `0x1800558c0`
- `0x180056144`
- `0x180059d40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030a64`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030b6d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030d2c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003105d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030a64`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030b6d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180030d2c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003105d`

## string_xrefs

- `0x180030706`: `hExternalIdentity=0x%p, flags=0x%llx, szTargetServiceUrl=%ls, szServicePolicy='%ls',szAdditionalPostParams=%ls`
- `0x180030b10`: `Could not get auth token, make sure identity is authenticated.`
- `0x180030e27`: `WLIDCGetSignedTokens call failed. hr=0x%x.`
- `0x180030fd6`: `Device token data: '%ls'`
- `0x180030e91`: `token=%ls`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall GetWebAuthUrlEx(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7)
{
  __int64 v11; // r8
  char v12; // r14
  CClientSingleIdentity *v13; // rbx
  void *v14; // rdi
  __int64 v15; // rcx
  _QWORD *HostingAppId; // rax
  _QWORD *v17; // rsi
  void *v18; // rbx
  unsigned __int16 *v19; // rsi
  unsigned int v20; // edx
  int v21; // eax
  void *v22; // rbx
  __int64 v23; // rbx
  __int64 v24; // rdi
  __int64 Lower; // rax
  __int64 v26; // rax
  int v27; // eax
  unsigned __int8 v28; // dl
  PPTraceStatus *v29; // rcx
  const unsigned __int16 *String; // rax
  unsigned __int16 *v31; // rbx
  unsigned __int16 *v33; // [rsp+20h] [rbp-158h]
  int IdentityFromExternalHandle_Internal; // [rsp+60h] [rbp-118h] BYREF
  unsigned __int16 *v35; // [rsp+68h] [rbp-110h] BYREF
  CClientSingleIdentity *v36; // [rsp+70h] [rbp-108h] BYREF
  unsigned __int16 *v37; // [rsp+78h] [rbp-100h] BYREF
  void *Block; // [rsp+80h] [rbp-F8h] BYREF
  __int64 v39; // [rsp+88h] [rbp-F0h] BYREF
  unsigned int v40[2]; // [rsp+90h] [rbp-E8h] BYREF
  __int64 v41; // [rsp+98h] [rbp-E0h] BYREF
  void *v42; // [rsp+A0h] [rbp-D8h] BYREF
  void *v43; // [rsp+A8h] [rbp-D0h] BYREF
  unsigned __int16 *v44; // [rsp+B0h] [rbp-C8h] BYREF
  unsigned __int16 *v45; // [rsp+B8h] [rbp-C0h] BYREF
  unsigned __int16 *v46; // [rsp+C0h] [rbp-B8h] BYREF
  char *v47; // [rsp+C8h] [rbp-B0h] BYREF
  char v48; // [rsp+D0h] [rbp-A8h]
  char *v49[4]; // [rsp+D8h] [rbp-A0h] BYREF
  int v50; // [rsp+F8h] [rbp-80h] BYREF
  _QWORD v51[3]; // [rsp+100h] [rbp-78h] BYREF
  char v52; // [rsp+118h] [rbp-60h]
  CPassportException *v53; // [rsp+120h] [rbp-58h] BYREF
  ATL::CAtlException *v54; // [rsp+128h] [rbp-50h] BYREF
  const wil::ResultException *v55; // [rsp+130h] [rbp-48h] BYREF

  IdentityFromExternalHandle_Internal = 0;
  CTraceFuncW<unsigned long>::CTraceFuncW<unsigned long>(
    v49,
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
    0x2E8u,
    (char *)&IdentityFromExternalHandle_Internal,
    "IDCRL::GetWebAuthUrlEx",
    L"hExternalIdentity=0x%p, flags=0x%llx, szTargetServiceUrl=%ls, szServicePolicy='%ls',szAdditionalPostParams=%ls",
    a1,
    a2,
    a3,
    a4,
    a5);
  v36 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v35);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v37);
  if ( !a6 )
  {
    TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp", 0x2F8u, L"pszWebAuthUrl is null.");
    IdentityFromExternalHandle_Internal = -2147024809;
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
    CAutoRefPtr<CAuthContext>::Deinit(&v36);
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
    return (unsigned int)IdentityFromExternalHandle_Internal;
  }
  if ( !a7 )
  {
    TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp", 0x2FFu, L"pszPostData is null");
    IdentityFromExternalHandle_Internal = -2147024809;
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
    CAutoRefPtr<CAuthContext>::Deinit(&v36);
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
    return (unsigned int)IdentityFromExternalHandle_Internal;
  }
  if ( a2 && (a2 & 0xFFFFFFFC) != 0 )
  {
    TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp", 0x306u, L"flags is invalid");
    IdentityFromExternalHandle_Internal = -2147024809;
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
    CAutoRefPtr<CAuthContext>::Deinit(&v36);
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
    return (unsigned int)IdentityFromExternalHandle_Internal;
  }
  IdentityFromExternalHandle_Internal = VerifyInitialized();
  if ( IdentityFromExternalHandle_Internal < 0 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
    CAutoRefPtr<CAuthContext>::Deinit(&v36);
    CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
    return (unsigned int)IdentityFromExternalHandle_Internal;
  }
  v12 = 1;
  LOBYTE(v11) = 1;
  try
  {
    IdentityFromExternalHandle_Internal = CClientIdentityStore::GetIdentityFromExternalHandle_Internal(
                                            g_pPPCRL + 8,
                                            a1,
                                            v11,
                                            &v36);
    if ( IdentityFromExternalHandle_Internal < 0 )
    {
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      CAutoRefPtr<CAuthContext>::Deinit(&v36);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
      return (unsigned int)IdentityFromExternalHandle_Internal;
    }
    v13 = v36;
    if ( !v36 )
    {
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x317u,
        L"Could not get internal identity handle, please check the passed in handle.");
      IdentityFromExternalHandle_Internal = -2147188704;
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      CAutoRefPtr<CAuthContext>::Deinit(&v36);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
      return (unsigned int)IdentityFromExternalHandle_Internal;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v41);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v46);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v39);
    v45 = 0;
    v44 = 0;
    Block = 0;
    v43 = 0;
    v14 = 0;
    v42 = 0;
    v47 = (char *)v13 + 16;
    v48 = 0;
    IdentityFromExternalHandle_Internal = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(&v47);
    if ( IdentityFromExternalHandle_Internal < 0 )
    {
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v47);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v42);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v43);
      if ( Block )
      {
        free(Block);
        Block = 0;
      }
LABEL_18:
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v44);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v45);
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v46 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      CAutoRefPtr<CAuthContext>::Deinit(&v36);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
      return (unsigned int)IdentityFromExternalHandle_Internal;
    }
    if ( !CClientSingleIdentity::HasAuthToken(v13) )
    {
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x32Bu,
        L"Could not get auth token, make sure identity is authenticated.");
      IdentityFromExternalHandle_Internal = -2147186591;
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v47);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v42);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v43);
      if ( Block )
      {
        free(Block);
        Block = 0;
      }
      goto LABEL_18;
    }
    HostingAppId = (_QWORD *)CClientPassportClientLibrary::GetHostingAppId(v15, v40);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &v46,
      *HostingAppId);
    ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)v40 - 24LL));
    v17 = (_QWORD *)((char *)v13 + 64);
    v18 = (void *)*((_QWORD *)v13 + 8);
    if ( !v18 )
    {
      v18 = operator new(0x28u);
      *((_QWORD *)v18 + 1) = 0;
      *((_DWORD *)v18 + 6) = 1;
      *(_QWORD *)v18 = &SmartWLIDHandle::`vftable'{for `SmartObj<void *>'};
      *((_QWORD *)v18 + 2) = &SmartWLIDHandle::`vftable'{for `CRefCounted'};
      *((_QWORD *)v18 + 4) = 0;
      CAutoRefPtr<SmartWLIDHandle>::Deinit(v17);
      *v17 = v18;
    }
    v19 = v46;
    IdentityFromExternalHandle_Internal = WLIDCGetOneTimeCredential(
                                            *((void *const *)v18 + 1),
                                            a2,
                                            v46,
                                            a3,
                                            a4,
                                            a5,
                                            &v44,
                                            &v45);
    if ( IdentityFromExternalHandle_Internal < 0 )
    {
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x340u,
        L"Could not generate web auth post data.");
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v47);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v42);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v43);
      if ( Block )
      {
        free(Block);
        Block = 0;
      }
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v44);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v45);
      ATL::CStringData::Release((ATL::CStringData *)(v39 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v41 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      CAutoRefPtr<CAuthContext>::Deinit(&v36);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
      return (unsigned int)IdentityFromExternalHandle_Internal;
    }
    v21 = WLIDCGetSignedTokens((struct _WLIDSignedTokens **)&Block, v20);
    IdentityFromExternalHandle_Internal = v21;
    if ( Block )
    {
      v22 = *(void **)Block;
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v43);
      v43 = v22;
      v14 = (void *)*((_QWORD *)Block + 1);
      CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v42);
      v42 = v14;
      v21 = IdentityFromExternalHandle_Internal;
    }
    if ( v21 >= 0 )
    {
      if ( v14 )
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v39);
        if ( !PPTraceShouldRedact() || (LOBYTE(v29) = 1, !PPTraceStatus::TraceOnFlag(v29, v28)) )
          v12 = 0;
        v51[0] = &PPRedactedStringW::`vftable';
        v23 = v39;
        v51[1] = v39;
        v51[2] = 0;
        v52 = v12;
        String = PPRedactedStringW::GetString((PPRedactedStringW *)v51);
        TracePrintW(
          5u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0x35Cu,
          L"Device token data: '%ls'",
          String);
        PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v51);
        goto LABEL_34;
      }
    }
    else
    {
      LODWORD(v33) = v21;
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x351u,
        L"WLIDCGetSignedTokens call failed. hr=0x%x.",
        v33);
      IdentityFromExternalHandle_Internal = 0;
    }
    v23 = v39;
LABEL_34:
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v41);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v35);
    UrlEscapeString(&v41);
    v24 = v41;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v37,
      L"token=%ls",
      v41);
    if ( *(int *)(v23 - 16) > 0 )
    {
      UrlEscapeString(&v39);
      v23 = v39;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v37,
        L"&sha1device=%ls",
        v39);
    }
    Lower = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v35);
    if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                         Lower,
                         L"?lc=") == -1 )
    {
      v26 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v35);
      if ( (unsigned int)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                           v26,
                           L"&lc=") == -1 )
      {
        v27 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                &v35,
                63,
                0);
        v40[0] = 1033;
        if ( v27 == -1 )
        {
          CStringSrv::GetLCID(v40);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &v35,
            L"?lc=%-d",
            v40[0]);
        }
        else
        {
          CStringSrv::GetLCID(v40);
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
            &v35,
            L"&lc=%-d",
            v40[0]);
        }
      }
    }
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v47);
    CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v42);
    CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(&v43);
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v44);
    CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>((void **)&v45);
    ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v19 - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
    TracePrintW(2u, "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp", 0x37Au, L"Web Auth URL: %ls", v35);
    v31 = v37;
    TracePrintW(
      2u,
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
      0x37Bu,
      L"Web Auth post data: %ls",
      v37);
    IdentityFromExternalHandle_Internal = CExternalMemoryManager::AllocateStringForExternal(
                                            (CExternalMemoryManager *)(g_pPPCRL + 58),
                                            v31,
                                            a7);
    if ( IdentityFromExternalHandle_Internal >= 0 )
    {
      IdentityFromExternalHandle_Internal = CExternalMemoryManager::AllocateStringForExternal(
                                              (CExternalMemoryManager *)(g_pPPCRL + 58),
                                              v35,
                                              a6);
      if ( IdentityFromExternalHandle_Internal < 0 )
        TracePrintW(
          2u,
          "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
          0x38Bu,
          L"Could not allocate memory for external string");
      ATL::CStringData::Release((ATL::CStringData *)(v31 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      CAutoRefPtr<CAuthContext>::Deinit(&v36);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
    }
    else
    {
      TracePrintW(
        2u,
        "clientcore\\ds\\ext\\live\\identity\\api\\classic\\ppcrl.cpp",
        0x383u,
        L"Could not allocate memory for external string");
      ATL::CStringData::Release((ATL::CStringData *)(v31 - 12));
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 12));
      CAutoRefPtr<CAuthContext>::Deinit(&v36);
      CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v49);
    }
  }
  catch ( CPassportException *v53 )
  {
    IdentityFromExternalHandle_Internal = *((_DWORD *)v53 + 2);
    if ( IdentityFromExternalHandle_Internal >= 0 )
      return (unsigned int)-2147418113;
    return (unsigned int)IdentityFromExternalHandle_Internal;
  }
  catch ( ATL::CAtlException *v54 )
  {
    IdentityFromExternalHandle_Internal = *(_DWORD *)v54;
    if ( IdentityFromExternalHandle_Internal >= 0 )
      return (unsigned int)-2147418113;
    return (unsigned int)IdentityFromExternalHandle_Internal;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( long v50 )
  {
    IdentityFromExternalHandle_Internal = v50;
    if ( v50 >= 0 )
      return (unsigned int)-2147418113;
    return (unsigned int)IdentityFromExternalHandle_Internal;
  }
  catch ( const wil::ResultException *v55 )
  {
    IdentityFromExternalHandle_Internal = *((_DWORD *)v55 + 8);
    if ( IdentityFromExternalHandle_Internal >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)IdentityFromExternalHandle_Internal;
}

```

## disassembly

```asm
0x1800306c0  push    rbx
0x1800306c2  push    rsi
0x1800306c3  push    rdi
0x1800306c4  push    r12
0x1800306c6  push    r13
0x1800306c8  push    r14
0x1800306ca  push    r15
0x1800306cc  sub     rsp, 140h
0x1800306d3  mov     r12, r9
0x1800306d6  mov     r13, r8
0x1800306d9  mov     r15, rdx
0x1800306dc  mov     rbx, rcx
0x1800306df  xor     esi, esi
0x1800306e1  mov     [rsp+178h+var_118], esi
0x1800306e5  mov     rax, [rsp+178h+arg_20]
0x1800306ed  mov     [rsp+178h+var_128], rax
0x1800306f2  mov     [rsp+178h+var_130], r9
0x1800306f7  mov     [rsp+178h+var_138], r8
0x1800306fc  mov     [rsp+178h+var_140], rdx
0x180030701  mov     [rsp+178h+var_148], rcx
0x180030706  lea     rax, aHexternalident; "hExternalIdentity=0x%p, flags=0x%llx, s"...
0x18003070d  mov     [rsp+178h+var_150], rax
0x180030712  lea     rax, aIdcrlGetwebaut; "IDCRL::GetWebAuthUrlEx"
0x180030719  mov     [rsp+178h+var_158], rax
0x18003071e  lea     r9, [rsp+178h+var_118]
0x180030723  mov     r8d, 2E8h
0x180030729  lea     rdi, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180030730  mov     rdx, rdi
0x180030733  lea     rcx, [rsp+178h+var_A0]
0x18003073b  call    ??0?$CTraceFuncW@K@@QEAA@PEBDKAEAK0PEBGZZ; CTraceFuncW<ulong>::CTraceFuncW<ulong>(char const *,ulong,ulong &,char const *,ushort const *,...)
0x180030740  nop
0x180030741  mov     [rsp+178h+var_108], rsi
0x180030746  lea     rcx, [rsp+178h+var_110]
0x18003074b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180030750  nop
0x180030751  lea     rcx, [rsp+178h+var_100]
0x180030756  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003075b  nop
0x18003075c  cmp     [rsp+178h+arg_28], rsi
0x180030764  jnz     short loc_1800307C2
0x180030766  lea     r9, aPszwebauthurlI; "pszWebAuthUrl is null."
0x18003076d  mov     r8d, 2F8h; unsigned int
0x180030773  mov     rdx, rdi; char *
0x180030776  lea     ecx, [rsi+2]; unsigned __int8
0x180030779  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18003077e  mov     [rsp+178h+var_118], 80070057h
0x180030786  mov     rcx, [rsp+178h+var_100]
0x18003078b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003078f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030794  nop
0x180030795  mov     rcx, [rsp+178h+var_110]
0x18003079a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003079e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800307a3  nop
0x1800307a4  lea     rcx, [rsp+178h+var_108]
0x1800307a9  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x1800307ae  nop
0x1800307af  lea     rcx, [rsp+178h+var_A0]
0x1800307b7  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800307bc  nop
0x1800307bd  jmp     loc_18003121D
0x1800307c2  cmp     [rsp+178h+arg_30], rsi
0x1800307ca  jnz     short loc_18003082A
0x1800307cc  lea     r9, aPszpostdataIsN; "pszPostData is null"
0x1800307d3  mov     r8d, 2FFh; unsigned int
0x1800307d9  mov     rdx, rdi; char *
0x1800307dc  mov     ecx, 2; unsigned __int8
0x1800307e1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800307e6  mov     [rsp+178h+var_118], 80070057h
0x1800307ee  mov     rcx, [rsp+178h+var_100]
0x1800307f3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800307f7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800307fc  nop
0x1800307fd  mov     rcx, [rsp+178h+var_110]
0x180030802  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030806  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003080b  nop
0x18003080c  lea     rcx, [rsp+178h+var_108]
0x180030811  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x180030816  nop
0x180030817  lea     rcx, [rsp+178h+var_A0]
0x18003081f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180030824  nop
0x180030825  jmp     loc_18003121D
0x18003082a  test    r15, r15
0x18003082d  jz      short loc_180030897
0x18003082f  mov     eax, 0FFFFFFFCh
0x180030834  test    rax, r15
0x180030837  jz      short loc_180030897
0x180030839  lea     r9, aFlagsIsInvalid; "flags is invalid"
0x180030840  mov     r8d, 306h; unsigned int
0x180030846  mov     rdx, rdi; char *
0x180030849  mov     ecx, 2; unsigned __int8
0x18003084e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180030853  mov     [rsp+178h+var_118], 80070057h
0x18003085b  mov     rcx, [rsp+178h+var_100]
0x180030860  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030864  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030869  nop
0x18003086a  mov     rcx, [rsp+178h+var_110]
0x18003086f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030873  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030878  nop
0x180030879  lea     rcx, [rsp+178h+var_108]
0x18003087e  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x180030883  nop
0x180030884  lea     rcx, [rsp+178h+var_A0]
0x18003088c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180030891  nop
0x180030892  jmp     loc_18003121D
0x180030897  call    ?VerifyInitialized@@YAJXZ; VerifyInitialized(void)
0x18003089c  mov     [rsp+178h+var_118], eax
0x1800308a0  test    eax, eax
0x1800308a2  jns     short loc_1800308E0
0x1800308a4  mov     rcx, [rsp+178h+var_100]
0x1800308a9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800308ad  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800308b2  nop
0x1800308b3  mov     rcx, [rsp+178h+var_110]
0x1800308b8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800308bc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800308c1  nop
0x1800308c2  lea     rcx, [rsp+178h+var_108]
0x1800308c7  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x1800308cc  nop
0x1800308cd  lea     rcx, [rsp+178h+var_A0]
0x1800308d5  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800308da  nop
0x1800308db  jmp     loc_18003121D
0x1800308e0  mov     rcx, cs:?g_pPPCRL@@3PEAVCClientPassportClientLibrary@@EA; CClientPassportClientLibrary * g_pPPCRL
0x1800308e7  add     rcx, 20h ; ' '
0x1800308eb  lea     r9, [rsp+178h+var_108]
0x1800308f0  mov     r14d, 1
0x1800308f6  mov     r8b, r14b
0x1800308f9  mov     rdx, rbx
0x1800308fc  call    ?GetIdentityFromExternalHandle_Internal@CClientIdentityStore@@QEAAJPEAU_tagPIH@IDCRL@@_NAEAV?$CAutoRefPtr@VCClientSingleIdentity@@@@@Z; CClientIdentityStore::GetIdentityFromExternalHandle_Internal(IDCRL::_tagPIH *,bool,CAutoRefPtr<CClientSingleIdentity> &)
0x180030901  mov     [rsp+178h+var_118], eax
0x180030905  test    eax, eax
0x180030907  jns     short loc_180030945
0x180030909  mov     rcx, [rsp+178h+var_100]
0x18003090e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030912  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030917  nop
0x180030918  mov     rcx, [rsp+178h+var_110]
0x18003091d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030921  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030926  nop
0x180030927  lea     rcx, [rsp+178h+var_108]
0x18003092c  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x180030931  nop
0x180030932  lea     rcx, [rsp+178h+var_A0]
0x18003093a  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003093f  nop
0x180030940  jmp     loc_18003121D
0x180030945  mov     rbx, [rsp+178h+var_108]
0x18003094a  test    rbx, rbx
0x18003094d  jnz     short loc_1800309AB
0x18003094f  lea     r9, aCouldNotGetInt; "Could not get internal identity handle,"...
0x180030956  mov     r8d, 317h; unsigned int
0x18003095c  mov     rdx, rdi; char *
0x18003095f  lea     ecx, [rbx+2]; unsigned __int8
0x180030962  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180030967  mov     [rsp+178h+var_118], 80048020h
0x18003096f  mov     rcx, [rsp+178h+var_100]
0x180030974  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030978  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003097d  nop
0x18003097e  mov     rcx, [rsp+178h+var_110]
0x180030983  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030987  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003098c  nop
0x18003098d  lea     rcx, [rsp+178h+var_108]
0x180030992  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x180030997  nop
0x180030998  lea     rcx, [rsp+178h+var_A0]
0x1800309a0  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800309a5  nop
0x1800309a6  jmp     loc_18003121D
0x1800309ab  lea     rcx, [rsp+178h+var_E0]
0x1800309b3  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800309b8  nop
0x1800309b9  lea     rcx, [rsp+178h+var_B8]
0x1800309c1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800309c6  nop
0x1800309c7  lea     rcx, [rsp+178h+var_F0]
0x1800309cf  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800309d4  nop
0x1800309d5  mov     [rsp+178h+var_C0], rsi
0x1800309dd  mov     [rsp+178h+var_C8], rsi
0x1800309e5  mov     [rsp+178h+Block], rsi
0x1800309ed  mov     [rsp+178h+var_D0], rsi
0x1800309f5  mov     rdi, rsi
0x1800309f8  mov     [rsp+178h+var_D8], rsi
0x180030a00  lea     rax, [rbx+10h]
0x180030a04  mov     [rsp+178h+var_B0], rax
0x180030a0c  mov     [rsp+178h+var_A8], sil
0x180030a14  lea     rcx, [rsp+178h+var_B0]
0x180030a1c  call    ?TryLock@?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAAJXZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::TryLock(void)
0x180030a21  mov     [rsp+178h+var_118], eax
0x180030a25  test    eax, eax
0x180030a27  jns     loc_180030B00
0x180030a2d  lea     rcx, [rsp+178h+var_B0]
0x180030a35  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180030a3a  nop
0x180030a3b  lea     rcx, [rsp+178h+var_D8]
0x180030a43  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030a48  nop
0x180030a49  lea     rcx, [rsp+178h+var_D0]
0x180030a51  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030a56  nop
0x180030a57  mov     rcx, [rsp+178h+Block]; Block
0x180030a5f  test    rcx, rcx
0x180030a62  jz      short loc_180030A72
0x180030a64  call    cs:__imp_free
0x180030a6a  mov     [rsp+178h+Block], rsi
0x180030a72  lea     rcx, [rsp+178h+var_C8]
0x180030a7a  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030a7f  nop
0x180030a80  lea     rcx, [rsp+178h+var_C0]
0x180030a88  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030a8d  nop
0x180030a8e  mov     rcx, [rsp+178h+var_F0]
0x180030a96  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030a9a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030a9f  nop
0x180030aa0  mov     rcx, [rsp+178h+var_B8]
0x180030aa8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030aac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ab1  nop
0x180030ab2  mov     rcx, [rsp+178h+var_E0]
0x180030aba  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030abe  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ac3  nop
0x180030ac4  mov     rcx, [rsp+178h+var_100]
0x180030ac9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030acd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ad2  nop
0x180030ad3  mov     rcx, [rsp+178h+var_110]
0x180030ad8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030adc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ae1  nop
0x180030ae2  lea     rcx, [rsp+178h+var_108]
0x180030ae7  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
0x180030aec  nop
0x180030aed  lea     rcx, [rsp+178h+var_A0]
0x180030af5  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180030afa  nop
0x180030afb  jmp     loc_18003121D
0x180030b00  mov     rcx, rbx; this
0x180030b03  call    ?HasAuthToken@CClientSingleIdentity@@QEAA_NXZ; CClientSingleIdentity::HasAuthToken(void)
0x180030b08  test    al, al
0x180030b0a  jnz     loc_180030C09
0x180030b10  lea     r9, aCouldNotGetAut; "Could not get auth token, make sure ide"...
0x180030b17  mov     r8d, 32Bh; unsigned int
0x180030b1d  lea     rdx, aClientcoreDsEx_1; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x180030b24  mov     ecx, 2; unsigned __int8
0x180030b29  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180030b2e  mov     [rsp+178h+var_118], 80048861h
0x180030b36  lea     rcx, [rsp+178h+var_B0]
0x180030b3e  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x180030b43  nop
0x180030b44  lea     rcx, [rsp+178h+var_D8]
0x180030b4c  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030b51  nop
0x180030b52  lea     rcx, [rsp+178h+var_D0]
0x180030b5a  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030b5f  nop
0x180030b60  mov     rcx, [rsp+178h+Block]; Block
0x180030b68  test    rcx, rcx
0x180030b6b  jz      short loc_180030B7B
0x180030b6d  call    cs:__imp_free
0x180030b73  mov     [rsp+178h+Block], rsi
0x180030b7b  lea     rcx, [rsp+178h+var_C8]
0x180030b83  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030b88  nop
0x180030b89  lea     rcx, [rsp+178h+var_C0]
0x180030b91  call    ??1?$CMIDLStringT@PEADPEBD@@QEAA@XZ; CMIDLStringT<char *,char const *>::~CMIDLStringT<char *,char const *>(void)
0x180030b96  nop
0x180030b97  mov     rcx, [rsp+178h+var_F0]
0x180030b9f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030ba3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ba8  nop
0x180030ba9  mov     rcx, [rsp+178h+var_B8]
0x180030bb1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030bb5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030bba  nop
0x180030bbb  mov     rcx, [rsp+178h+var_E0]
0x180030bc3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030bc7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030bcc  nop
0x180030bcd  mov     rcx, [rsp+178h+var_100]
0x180030bd2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030bd6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030bdb  nop
0x180030bdc  mov     rcx, [rsp+178h+var_110]
0x180030be1  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180030be5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030bea  nop
0x180030beb  lea     rcx, [rsp+178h+var_108]
0x180030bf0  call    ?Deinit@?$CAutoRefPtr@VCAuthContext@@@@IEAAXXZ; CAutoRefPtr<CAuthContext>::Deinit(void)
  ... truncated ...
```
