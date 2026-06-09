# HandlePersistCredential(void * const,ushort const *,unsigned __int64,ushort * *)

- ea: `0x1800b67b0`
- end: `0x1800b702f`
- name: `?HandlePersistCredential@@YAJQEAXPEBG_KPEAPEAG@Z`
- size: `2175`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004f660`
- `0x18009ef98`
- `0x1800b7f6c`
- `0x1800f0dd0`

## callees

- `0x18000c050`
- `0x18000cfac`
- `0x18000e8dc`
- `0x18000ed04`
- `0x18000ed3c`
- `0x18000fd04`
- `0x180011f38`
- `0x1800124c4`
- `0x1800151c4`
- `0x180015fdc`
- `0x1800179c0`
- `0x1800181bc`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f968`
- `0x180020970`
- `0x180020b10`
- `0x180028770`
- `0x180028cd4`
- `0x18003ba08`
- `0x18003e564`
- `0x18003ec18`
- `0x180043344`
- `0x180045af8`
- `0x180046aa4`
- `0x180046c18`
- `0x180048004`
- `0x18004aff8`
- `0x18005538c`
- `0x18007687c`
- `0x18007c38c`
- `0x1800801dc`
- `0x180081cac`
- `0x1800834d8`
- `0x180084374`
- `0x180084e88`
- `0x180086c9c`
- `0x18008964c`
- `0x1800a716c`
- `0x1800b67b0`
- `0x1800d82a4`
- `0x1800daeb0`
- `0x1800db174`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b694e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b69e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b6dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b6e88`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b694e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b69e8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b6dd0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b6e88`

## string_xrefs

- `0x1800b6819`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800b688c`: `hr = client.ImpersonateClient()`
- `0x1800b6bd5`: `hr = client.GetTokenUser(pszSid)`
- `0x1800b6d8b`: `hr = Transaction.Commit()`
- `0x1800b6a74`: `g_pPPCRL->GetNegativeCacheManager()->ClearNegativeCacheData(pIdentity, daCreatedTime.GetTime())`
- `0x1800b6d2f`: `hr = pIdentity->DeLinkCertObject(DEFAULT_CRED_SLC, &pTempCert)`
- `0x1800b6df0`: `hr = pIdentity->PersistServiceTokens()`
- `0x1800b6ea8`: `hr = pIdentity->RemovePersistedServiceTokens()`
- `0x1800b6ed1`: `hr = pIdentity->RemovePersistedCertificates()`

## pseudocode

```c
__int64 __fastcall HandlePersistCredential(
        void *const a1,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned __int16 **a4)
{
  unsigned __int64 v7; // r8
  int v8; // eax
  int LogonId; // eax
  int SingleIdentity; // eax
  CSingleIdentity *v11; // rbx
  bool v12; // si
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rdi
  int v19; // eax
  CIdentityCredentialBag *v20; // rax
  int v21; // eax
  __int64 v22; // r8
  int v23; // r8d
  int v24; // r9d
  int v25; // r14d
  int TokenUser; // eax
  void *v27; // rsi
  int v28; // edi
  int v29; // eax
  volatile signed __int32 *v30; // rdi
  int v31; // eax
  const char *v32; // rcx
  unsigned int v33; // r8d
  struct CCertObject *v34; // rsi
  struct CCertObject **v35; // rdi
  int v36; // eax
  int v37; // eax
  unsigned int i; // esi
  CSingleIdentity **v39; // rax
  CSingleIdentity **v40; // rax
  int v41; // eax
  int v42; // eax
  char *v43; // rdi
  unsigned int v44; // esi
  CSingleIdentity **v45; // rax
  CSingleIdentity **v46; // rax
  _QWORD *v47; // rax
  _QWORD *v48; // rax
  __int64 v49; // rbx
  __int64 v50; // rax
  CSingleIdentity **v51; // rax
  CSingleIdentity **v52; // rax
  unsigned int v53; // ebx
  __int64 v55; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v56; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  struct _LUID v59; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h] BYREF
  struct CCertObject *v61; // [rsp+70h] [rbp-90h] BYREF
  CSingleIdentity *v62; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h] BYREF
  struct CCertObject *v64; // [rsp+88h] [rbp-78h] BYREF
  char v65[8]; // [rsp+98h] [rbp-68h] BYREF
  void *v66; // [rsp+A0h] [rbp-60h]
  __int64 *v67; // [rsp+A8h] [rbp-58h]
  _BYTE v68[64]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v69[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v70[48]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v71; // [rsp+140h] [rbp+40h]
  _BYTE v72[176]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v73; // [rsp+298h] [rbp+198h] BYREF

  v73 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v57,
    a2);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v69,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    5786,
    &v73,
    "HandlePersistCredential",
    L"wszCredType='%ls'",
    v57);
  v59 = 0;
  v62 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v65);
  v61 = 0;
  v64 = 0;
  v60 = 0;
  if ( a4 )
    *a4 = 0;
  SmartPerformanceTelemetryJson::SmartPerformanceTelemetryJson((SmartPerformanceTelemetryJson *)v72, a4, v7, a3, L"pc");
  v8 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v60, 0);
  v73 = v8;
  if ( v8 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandlePersistCredential",
      0x16B3u,
      v8,
      "hr = client.ImpersonateClient()");
    goto LABEL_78;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v60, &v59);
  v73 = LogonId;
  if ( LogonId < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandlePersistCredential",
      0x16B4u,
      LogonId,
      "hr = client.GetLogonId(logonId)");
    goto LABEL_78;
  }
  SingleIdentity = CIdentityStore::GetSingleIdentity((char *)g_pPPCRL + 496, &v59, a1, &v62);
  v73 = SingleIdentity;
  if ( SingleIdentity < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandlePersistCredential",
      0x16B6u,
      SingleIdentity,
      "hr = g_pPPCRL->GetIdentityStore()->GetSingleIdentity(logonId, handle, pIdentity)");
    goto LABEL_78;
  }
  v11 = v62;
  if ( !*((_BYTE *)v62 + 564) )
  {
    v73 = -2147188624;
    goto LABEL_78;
  }
  if ( *((_DWORD *)v62 + 184) && (unsigned int)_o__wcsicmp(v57, L"ps:password") )
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x16C4u,
      L"Skipping deletion of credentials for connected account.");
    goto LABEL_78;
  }
  v12 = 0;
  if ( *((_BYTE *)v11 + 627) == 1 && *((_BYTE *)v11 + 269) == 1 )
    v12 = !CSingleIdentity::HasAuthToken(v11);
  v13 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v11 + 8LL))(v11);
  v14 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v55,
          &v57);
  LOBYTE(v15) = v12;
  v73 = CIdentityCredentialBag::PersistCredential(v13, v15, v14);
  if ( v73 >= 0
    && !(unsigned int)_o__wcsicmp(v57, L"ps:password")
    && !(*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v11 + 80LL))(v11)
    && CSingleIdentity::HasAuthToken(v11) )
  {
    CPPCRLToken::CPPCRLToken((CPPCRLToken *)v70);
    v16 = *((_QWORD *)v11 + 11);
    v17 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
            &v55,
            L"http://Passport.NET/tb");
    if ( (unsigned int)CIdentityTokenBag::RetrieveToken(v16, v17, v70) )
    {
      v18 = v71;
      v19 = NegativeCacheManager::ClearNegativeCacheData((CPassportClientLibrary *)((char *)g_pPPCRL + 2312), v11, v71);
      if ( v19 < 0 )
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandlePersistCredential",
          0x16E0u,
          v19,
          "g_pPPCRL->GetNegativeCacheManager()->ClearNegativeCacheData(pIdentity, daCreatedTime.GetTime())");
      ATL::CTime::GetTickCount(&v55);
      if ( v55 - *((int *)CClientConfigDataCacheManager::theConfigDataManager() + 68) - v18 >= 120 )
      {
        if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
        {
          v55 = 50331648;
          v63 = v22;
          v58 = v18;
          LODWORD(v56) = *((_DWORD *)CClientConfigDataCacheManager::theConfigDataManager() + 68);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            (_DWORD)v56,
            (unsigned int)byte_180197CCB,
            v23,
            v24,
            (__int64)&v56,
            (__int64)&v58,
            (__int64)&v63,
            (__int64)&v55);
        }
      }
      else
      {
        v20 = (CIdentityCredentialBag *)(*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v11 + 8LL))(v11);
        v21 = CIdentityCredentialBag::SetPropertyDefaultCredSavedToPersisted(v20);
        if ( v21 < 0 )
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "HandlePersistCredential",
            0x16E6u,
            v21,
            "pIdentity->GetCredBag()->SetPropertyDefaultCredSavedToPersisted()");
      }
    }
    CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v70);
  }
  if ( v73 >= 0 && v73 != 297058 )
  {
    v25 = a3 & 1;
    if ( !v25 )
      goto LABEL_56;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
    v56 = 0;
    TokenUser = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v60, &v55);
    v73 = TokenUser;
    if ( TokenUser < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandlePersistCredential",
        0x1700u,
        TokenUser,
        "hr = client.GetTokenUser(pszSid)");
LABEL_36:
      CAutoRefPtr<IStoredIdentity>::Deinit(&v56);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
      goto LABEL_78;
    }
    v27 = operator new(0x120u, (const struct std::nothrow_t *)std::nothrow);
    v66 = v27;
    if ( v27 )
    {
      v67 = &v58;
      v28 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v58,
              &v55);
      v29 = (*(__int64 (__fastcall **)(CSingleIdentity *, __int64 *))(*(_QWORD *)v11 + 32LL))(v11, &v63);
      v30 = (volatile signed __int32 *)CStoredIdentity::CStoredIdentity((_DWORD)v27, v29, v28, (unsigned int)&v59, 0);
    }
    else
    {
      v30 = 0;
    }
    CAutoRefPtr<IStoredIdentity>::Deinit(&v56);
    v56 = v30;
    if ( !v30 )
    {
      v73 = -2147024882;
      goto LABEL_36;
    }
    v59 = (struct _LUID)v30;
    _InterlockedIncrement(v30 + 2);
    CStoredIdentityTransaction::CStoredIdentityTransaction(v68, &v59);
    v31 = CStoredIdentityTransaction::Start((CStoredIdentityTransaction *)v68);
    v73 = v31;
    if ( v31 < 0 )
    {
      v32 = "hr = Transaction.Start()";
      v33 = 5898;
LABEL_44:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandlePersistCredential",
        v33,
        v31,
        v32);
      CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v68);
      goto LABEL_36;
    }
    if ( !(*(unsigned int (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v30 + 16LL))(v30, 0) )
    {
LABEL_55:
      CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v68);
      CAutoRefPtr<IStoredIdentity>::Deinit(&v56);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
LABEL_56:
      CSingleIdentity::SaveExtProperties(v11);
      if ( (unsigned int)_o__wcsicmp(v57, L"ps:password") )
      {
        if ( !(unsigned int)_o__wcsicmp(v57, L"ps:membernameonly") )
        {
          v41 = CSingleIdentity::RemovePersistedServiceTokens(v11);
          v73 = v41;
          if ( v41 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              "HandlePersistCredential",
              0x173Du,
              v41,
              "hr = pIdentity->RemovePersistedServiceTokens()");
            goto LABEL_78;
          }
          v42 = CSingleIdentity::RemovePersistedCertificates(v11);
          v73 = v42;
          if ( v42 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              "HandlePersistCredential",
              0x173Eu,
              v42,
              "hr = pIdentity->RemovePersistedCertificates()");
            goto LABEL_78;
          }
          v43 = (char *)v11 + 568;
          v44 = 0;
          if ( *((_QWORD *)v11 + 72) )
          {
            do
            {
              v45 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                          v43,
                                          v44);
              if ( !CSingleIdentity::HasAuthToken(*v45)
                || (v46 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                                v43,
                                                v44),
                    CSingleIdentity::GetIsLinkedHandle(*v46)) )
              {
                v47 = (_QWORD *)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                  v43,
                                  v44);
                if ( !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v47 + 8LL))(*v47)
                  || (v48 = (_QWORD *)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                        v43,
                                        v44),
                      v49 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v48 + 8LL))(*v48),
                      v50 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                              &v58,
                              L"ps:password"),
                      !(unsigned __int8)CIdentityCredentialBag::HasPersistedCredential(v49, v50)) )
                {
                  v51 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                              v43,
                                              v44);
                  CSingleIdentity::RemovePersistedServiceTokens(*v51);
                  v52 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                              v43,
                                              v44);
                  CSingleIdentity::RemovePersistedCertificates(*v52);
                }
              }
              ++v44;
            }
            while ( (unsigned __int64)v44 < *((_QWORD *)v43 + 1) );
          }
        }
      }
      else
      {
        v36 = CSingleIdentity::PersistServiceTokens(v11);
        v73 = v36;
        if ( v36 < 0 )
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "HandlePersistCredential",
            0x1726u,
            v36,
            "hr = pIdentity->PersistServiceTokens()");
          goto LABEL_78;
        }
        if ( !v25 )
        {
          v37 = CSingleIdentity::PersistCertificates(v11);
          v73 = v37;
          if ( v37 < 0 )
          {
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              "HandlePersistCredential",
              0x172Eu,
              v37,
              "hr = pIdentity->PersistCertificates()");
            goto LABEL_78;
          }
        }
        for ( i = 0; (unsigned __int64)i < *((_QWORD *)v11 + 72); ++i )
        {
          v39 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                      (char *)v11 + 568,
                                      i);
          CSingleIdentity::PersistServiceTokens(*v39);
          v40 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                      (char *)v11 + 568,
                                      i);
          CSingleIdentity::PersistCertificates(*v40);
        }
      }
      v73 = 0;
      goto LABEL_78;
    }
    v31 = CSingleIdentity::DeLinkCertObject(v11, L"Windows_Default_Cred_SLC", &v64);
    v73 = v31;
    if ( v31 < 0 )
    {
      v32 = "hr = pIdentity->DeLinkCertObject(DEFAULT_CRED_SLC, &pTempCert)";
      v33 = 5906;
      goto LABEL_44;
    }
    v34 = v64;
    v61 = v64;
    v35 = (struct CCertObject **)(v30 + 32);
    if ( *v35 == v64 )
    {
      if ( v35 == &v61 )
        goto LABEL_53;
    }
    else
    {
      ATL::CAutoPtr<CCertObject>::Free(v35);
      *v35 = v34;
    }
    v61 = 0;
LABEL_53:
    v73 = 0;
    v31 = CStoredIdentityTransaction::Commit((CStoredIdentityTransaction *)v68, 0, 0);
    v73 = v31;
    if ( v31 < 0 )
    {
      v32 = "hr = Transaction.Commit()";
      v33 = 5913;
      goto LABEL_44;
    }
    goto LABEL_55;
  }
LABEL_78:
  v53 = v73;
  SmartPerformanceTelemetryJson::~SmartPerformanceTelemetryJson((SmartPerformanceTelemetryJson *)v72);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v60);
  ATL::CAutoPtr<CCertObject>::Free(&v61);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v65);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v62);
  CTraceFuncW<long>::~CTraceFuncW<long>(v69);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
  return v53;
}

```

## disassembly

```asm
0x1800b67b0  push    rbp
0x1800b67b2  push    rbx
0x1800b67b3  push    rsi
0x1800b67b4  push    rdi
0x1800b67b5  push    r12
0x1800b67b7  push    r13
0x1800b67b9  push    r14
0x1800b67bb  push    r15
0x1800b67bd  lea     rbp, [rsp-138h]
0x1800b67c5  sub     rsp, 238h
0x1800b67cc  mov     rbx, r9
0x1800b67cf  mov     r14, r8
0x1800b67d2  mov     rdi, rcx
0x1800b67d5  xor     r15d, r15d
0x1800b67d8  mov     [rbp+170h+arg_18], r15d
0x1800b67df  lea     rcx, [rsp+270h+var_220]
0x1800b67e4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800b67e9  nop
0x1800b67ea  mov     rax, [rsp+270h+var_220]
0x1800b67ef  mov     [rsp+270h+var_240], rax
0x1800b67f4  lea     rax, aWszcredtypeLs; "wszCredType='%ls'"
0x1800b67fb  mov     [rsp+270h+var_248], rax
0x1800b6800  lea     r13, aHandlepersistc; "HandlePersistCredential"
0x1800b6807  mov     [rsp+270h+var_250], r13
0x1800b680c  lea     r9, [rbp+170h+arg_18]
0x1800b6813  mov     r8d, 169Ah
0x1800b6819  lea     r12, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800b6820  mov     rdx, r12
0x1800b6823  lea     rcx, [rbp+170h+var_180]
0x1800b6827  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x1800b682c  nop
0x1800b682d  mov     qword ptr [rsp+270h+var_210.LowPart], r15
0x1800b6832  mov     [rsp+270h+var_1F8], r15
0x1800b6837  lea     rcx, [rbp+170h+var_1D8]
0x1800b683b  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b6840  nop
0x1800b6841  mov     [rsp+270h+var_200], r15
0x1800b6846  mov     [rbp+170h+var_1E8], r15
0x1800b684a  mov     [rsp+270h+var_208], r15
0x1800b684f  test    rbx, rbx
0x1800b6852  jz      short loc_1800B6857
0x1800b6854  mov     [rbx], r15
0x1800b6857  lea     rax, aPc; "pc"
0x1800b685e  mov     [rsp+270h+var_250], rax; unsigned __int16 *
0x1800b6863  mov     r9, r14; unsigned __int64
0x1800b6866  mov     rdx, rbx; unsigned __int16 **
0x1800b6869  lea     rcx, [rbp+170h+var_B0]; this
0x1800b6870  call    ??0SmartPerformanceTelemetryJson@@QEAA@PEAPEAG_K1PEBG@Z; SmartPerformanceTelemetryJson::SmartPerformanceTelemetryJson(ushort * *,unsigned __int64,unsigned __int64,ushort const *)
0x1800b6875  nop
0x1800b6876  xor     edx, edx; struct ATL::CAccessToken *
0x1800b6878  lea     rcx, [rsp+270h+var_208]; this
0x1800b687d  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x1800b6882  mov     [rbp+170h+arg_18], eax
0x1800b6888  test    eax, eax
0x1800b688a  jns     short loc_1800B68B1
0x1800b688c  lea     r8, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x1800b6893  mov     [rsp+270h+var_250], r8; char *
0x1800b6898  mov     r8d, 16B3h; unsigned int
0x1800b689e  mov     r9d, eax; int
0x1800b68a1  mov     rdx, r13; char *
0x1800b68a4  mov     rcx, r12; char *
0x1800b68a7  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800b68ac  jmp     loc_1800B6FC7
0x1800b68b1  lea     rdx, [rsp+270h+var_210]; struct _LUID *
0x1800b68b6  lea     rcx, [rsp+270h+var_208]; this
0x1800b68bb  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x1800b68c0  mov     [rbp+170h+arg_18], eax
0x1800b68c6  test    eax, eax
0x1800b68c8  jns     short loc_1800B68DE
0x1800b68ca  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x1800b68d1  mov     [rsp+270h+var_250], rcx
0x1800b68d6  mov     r8d, 16B4h
0x1800b68dc  jmp     short loc_1800B689E
0x1800b68de  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800b68e5  add     rcx, 1F0h
0x1800b68ec  lea     r9, [rsp+270h+var_1F8]
0x1800b68f1  mov     r8, rdi
0x1800b68f4  lea     rdx, [rsp+270h+var_210]
0x1800b68f9  call    ?GetSingleIdentity@CIdentityStore@@QEAAJAEAU_LUID@@PEAXAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::GetSingleIdentity(_LUID &,void *,CAutoRefPtr<CSingleIdentity> &)
0x1800b68fe  mov     [rbp+170h+arg_18], eax
0x1800b6904  test    eax, eax
0x1800b6906  jns     short loc_1800B691C
0x1800b6908  lea     rcx, aHrGPppcrlGetid_29; "hr = g_pPPCRL->GetIdentityStore()->GetS"...
0x1800b690f  mov     [rsp+270h+var_250], rcx
0x1800b6914  mov     r8d, 16B6h
0x1800b691a  jmp     short loc_1800B689E
0x1800b691c  mov     rbx, [rsp+270h+var_1F8]
0x1800b6921  cmp     [rbx+234h], r15b
0x1800b6928  jnz     short loc_1800B6939
0x1800b692a  mov     [rbp+170h+arg_18], 80048070h
0x1800b6934  jmp     loc_1800B6FC7
0x1800b6939  cmp     [rbx+2E0h], r15d
0x1800b6940  jz      short loc_1800B6977
0x1800b6942  lea     rdx, aPsPassword_0; "ps:password"
0x1800b6949  mov     rcx, [rsp+270h+var_220]
0x1800b694e  call    cs:__imp__o__wcsicmp
0x1800b6954  test    eax, eax
0x1800b6956  jz      short loc_1800B6977
0x1800b6958  lea     r9, aSkippingDeleti; "Skipping deletion of credentials for co"...
0x1800b695f  mov     r8d, 16C4h; unsigned int
0x1800b6965  mov     rdx, r12; char *
0x1800b6968  mov     ecx, 5; unsigned __int8
0x1800b696d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800b6972  jmp     loc_1800B6FC7
0x1800b6977  movzx   esi, r15b
0x1800b697b  mov     edi, 1
0x1800b6980  cmp     [rbx+273h], dil
0x1800b6987  jnz     short loc_1800B699F
0x1800b6989  cmp     [rbx+10Dh], dil
0x1800b6990  jnz     short loc_1800B699F
0x1800b6992  mov     rcx, rbx; this
0x1800b6995  call    ?HasAuthToken@CSingleIdentity@@QEAA_NXZ; CSingleIdentity::HasAuthToken(void)
0x1800b699a  test    al, al
0x1800b699c  cmovz   esi, edi
0x1800b699f  mov     rax, [rbx]
0x1800b69a2  mov     rcx, rbx
0x1800b69a5  mov     rax, [rax+8]
0x1800b69a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b69ae  mov     rdi, rax
0x1800b69b1  lea     rdx, [rsp+270h+var_220]
0x1800b69b6  lea     rcx, [rsp+270h+var_230]
0x1800b69bb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800b69c0  mov     r8, rax
0x1800b69c3  mov     dl, sil
0x1800b69c6  mov     rcx, rdi
0x1800b69c9  call    ?PersistCredential@CIdentityCredentialBag@@QEAAJ_NV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CIdentityCredentialBag::PersistCredential(bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x1800b69ce  mov     [rbp+170h+arg_18], eax
0x1800b69d4  test    eax, eax
0x1800b69d6  js      loc_1800B6B82
0x1800b69dc  lea     rdx, aPsPassword_0; "ps:password"
0x1800b69e3  mov     rcx, [rsp+270h+var_220]
0x1800b69e8  call    cs:__imp__o__wcsicmp
0x1800b69ee  test    eax, eax
0x1800b69f0  jnz     loc_1800B6B82
0x1800b69f6  mov     rax, [rbx]
0x1800b69f9  mov     rcx, rbx
0x1800b69fc  mov     rax, [rax+50h]
0x1800b6a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6a05  test    eax, eax
0x1800b6a07  jnz     loc_1800B6B82
0x1800b6a0d  mov     rcx, rbx; this
0x1800b6a10  call    ?HasAuthToken@CSingleIdentity@@QEAA_NXZ; CSingleIdentity::HasAuthToken(void)
0x1800b6a15  cmp     al, 1
0x1800b6a17  jnz     loc_1800B6B82
0x1800b6a1d  lea     rcx, [rbp+170h+var_160]; this
0x1800b6a21  call    ??0CPPCRLToken@@QEAA@XZ; CPPCRLToken::CPPCRLToken(void)
0x1800b6a26  nop
0x1800b6a27  mov     rdi, [rbx+58h]
0x1800b6a2b  lea     rdx, aHttpPassportNe_2; "http://Passport.NET/tb"
0x1800b6a32  lea     rcx, [rsp+270h+var_230]
0x1800b6a37  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x1800b6a3c  lea     r8, [rbp+170h+var_160]
0x1800b6a40  mov     rdx, rax
0x1800b6a43  mov     rcx, rdi
0x1800b6a46  call    ?RetrieveToken@CIdentityTokenBag@@QEAAHV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@AEAVCPPCRLToken@@@Z; CIdentityTokenBag::RetrieveToken(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CPPCRLToken &)
0x1800b6a4b  test    eax, eax
0x1800b6a4d  jz      loc_1800B6B79
0x1800b6a53  mov     rdi, [rbp+170h+var_130]
0x1800b6a57  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800b6a5e  add     rcx, 908h; this
0x1800b6a65  mov     r8, rdi; __int64
0x1800b6a68  mov     rdx, rbx; struct ISingleIdentity *
0x1800b6a6b  call    ?ClearNegativeCacheData@NegativeCacheManager@@QEAAJPEAVISingleIdentity@@_J@Z; NegativeCacheManager::ClearNegativeCacheData(ISingleIdentity *,__int64)
0x1800b6a70  test    eax, eax
0x1800b6a72  jns     short loc_1800B6A94
0x1800b6a74  lea     rcx, aGPppcrlGetnega_5; "g_pPPCRL->GetNegativeCacheManager()->Cl"...
0x1800b6a7b  mov     [rsp+270h+var_250], rcx; char *
0x1800b6a80  mov     r9d, eax; int
0x1800b6a83  mov     r8d, 16E0h; unsigned int
0x1800b6a89  mov     rdx, r13; char *
0x1800b6a8c  mov     rcx, r12; char *
0x1800b6a8f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800b6a94  lea     rcx, [rsp+270h+var_230]
0x1800b6a99  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x1800b6a9e  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x1800b6aa3  movsxd  rcx, dword ptr [rax+110h]
0x1800b6aaa  mov     r8, [rsp+270h+var_230]
0x1800b6aaf  mov     rax, r8
0x1800b6ab2  sub     rax, rcx
0x1800b6ab5  sub     rax, rdi
0x1800b6ab8  cmp     rax, 78h ; 'x'
0x1800b6abc  jge     short loc_1800B6AFF
0x1800b6abe  mov     rax, [rbx]
0x1800b6ac1  mov     rcx, rbx
0x1800b6ac4  mov     rax, [rax+8]
0x1800b6ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6acd  mov     rcx, rax; this
0x1800b6ad0  call    ?SetPropertyDefaultCredSavedToPersisted@CIdentityCredentialBag@@QEAAJXZ; CIdentityCredentialBag::SetPropertyDefaultCredSavedToPersisted(void)
0x1800b6ad5  test    eax, eax
0x1800b6ad7  jns     loc_1800B6B79
0x1800b6add  lea     rcx, aPidentityGetcr; "pIdentity->GetCredBag()->SetPropertyDef"...
0x1800b6ae4  mov     [rsp+270h+var_250], rcx; char *
0x1800b6ae9  mov     r9d, eax; int
0x1800b6aec  mov     r8d, 16E6h; unsigned int
0x1800b6af2  mov     rdx, r13; char *
0x1800b6af5  mov     rcx, r12; char *
0x1800b6af8  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800b6afd  jmp     short loc_1800B6B79
0x1800b6aff  mov     eax, cs:dword_1801C2080
0x1800b6b05  cmp     eax, 5
0x1800b6b08  jbe     short loc_1800B6B79
0x1800b6b0a  mov     rdx, 400000000000h
0x1800b6b14  lea     rcx, dword_1801C2080
0x1800b6b1b  call    _tlgKeywordOn
0x1800b6b20  test    al, al
0x1800b6b22  jz      short loc_1800B6B79
0x1800b6b24  mov     [rsp+270h+var_230], 3000000h
0x1800b6b2d  mov     [rbp+170h+var_1F0], r8
0x1800b6b31  mov     [rsp+270h+var_218], rdi
0x1800b6b36  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x1800b6b3b  mov     ecx, [rax+110h]
0x1800b6b41  mov     dword ptr [rsp+270h+var_228], ecx
0x1800b6b45  lea     rax, [rsp+270h+var_230]
0x1800b6b4a  mov     [rsp+270h+var_238], rax
0x1800b6b4f  lea     rax, [rbp+170h+var_1F0]
0x1800b6b53  mov     [rsp+270h+var_240], rax
0x1800b6b58  lea     rax, [rsp+270h+var_218]
0x1800b6b5d  mov     [rsp+270h+var_248], rax
0x1800b6b62  lea     rax, [rsp+270h+var_228]
0x1800b6b67  mov     [rsp+270h+var_250], rax
0x1800b6b6c  lea     rdx, byte_180197CCB
0x1800b6b73  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800b6b78  nop
0x1800b6b79  lea     rcx, [rbp+170h+var_160]; this
0x1800b6b7d  call    ??1CPPCRLToken@@QEAA@XZ; CPPCRLToken::~CPPCRLToken(void)
0x1800b6b82  test    [rbp+170h+arg_18], 80000000h
0x1800b6b8c  jnz     loc_1800B6FC7
0x1800b6b92  cmp     [rbp+170h+arg_18], 48862h
0x1800b6b9c  jz      loc_1800B6FC7
0x1800b6ba2  and     r14d, 1
0x1800b6ba6  jz      loc_1800B6DBC
0x1800b6bac  lea     rcx, [rsp+270h+var_230]
0x1800b6bb1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b6bb6  nop
0x1800b6bb7  mov     [rsp+270h+var_228], r15
0x1800b6bbc  lea     rdx, [rsp+270h+var_230]
0x1800b6bc1  lea     rcx, [rsp+270h+var_208]; this
0x1800b6bc6  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800b6bcb  mov     [rbp+170h+arg_18], eax
0x1800b6bd1  test    eax, eax
0x1800b6bd3  jns     short loc_1800B6C10
0x1800b6bd5  lea     rcx, aHrClientGettok_1; "hr = client.GetTokenUser(pszSid)"
0x1800b6bdc  mov     [rsp+270h+var_250], rcx; char *
0x1800b6be1  mov     r9d, eax; int
0x1800b6be4  mov     r8d, 1700h; unsigned int
0x1800b6bea  mov     rdx, r13; char *
0x1800b6bed  mov     rcx, r12; char *
0x1800b6bf0  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800b6bf5  nop
0x1800b6bf6  lea     rcx, [rsp+270h+var_228]
0x1800b6bfb  call    ?Deinit@?$CAutoRefPtr@VIStoredIdentity@@@@IEAAXXZ; CAutoRefPtr<IStoredIdentity>::Deinit(void)
0x1800b6c00  nop
0x1800b6c01  lea     rcx, [rsp+270h+var_230]
0x1800b6c06  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800b6c0b  jmp     loc_1800B6FC7
0x1800b6c10  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b6c17  mov     ecx, 120h; unsigned __int64
0x1800b6c1c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b6c21  mov     rsi, rax
0x1800b6c24  mov     [rbp+170h+var_1D0], rax
0x1800b6c28  test    rax, rax
0x1800b6c2b  jz      short loc_1800B6C79
0x1800b6c2d  lea     rax, [rsp+270h+var_218]
0x1800b6c32  mov     [rbp+170h+var_1C8], rax
0x1800b6c36  lea     rdx, [rsp+270h+var_230]
0x1800b6c3b  lea     rcx, [rsp+270h+var_218]
0x1800b6c40  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800b6c45  mov     rdi, rax
0x1800b6c48  mov     rcx, [rbx]
0x1800b6c4b  mov     rax, [rcx+20h]
0x1800b6c4f  lea     rdx, [rbp+170h+var_1F0]
0x1800b6c53  mov     rcx, rbx
0x1800b6c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6c5b  nop
0x1800b6c5c  mov     dword ptr [rsp+270h+var_250], r15d
0x1800b6c61  lea     r9, [rsp+270h+var_210]
0x1800b6c66  mov     r8, rdi
0x1800b6c69  mov     rdx, rax
0x1800b6c6c  mov     rcx, rsi
0x1800b6c6f  call    ??0CStoredIdentity@@QEAA@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEAU_LUID@@H@Z; CStoredIdentity::CStoredIdentity(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_LUID &,int)
0x1800b6c74  mov     rdi, rax
0x1800b6c77  jmp     short loc_1800B6C7C
0x1800b6c79  mov     rdi, r15
0x1800b6c7c  lea     rcx, [rsp+270h+var_228]
0x1800b6c81  call    ?Deinit@?$CAutoRefPtr@VIStoredIdentity@@@@IEAAXXZ; CAutoRefPtr<IStoredIdentity>::Deinit(void)
0x1800b6c86  mov     [rsp+270h+var_228], rdi
0x1800b6c8b  test    rdi, rdi
0x1800b6c8e  jnz     short loc_1800B6C9F
0x1800b6c90  mov     [rbp+170h+arg_18], 8007000Eh
0x1800b6c9a  jmp     loc_1800B6BF6
0x1800b6c9f  mov     qword ptr [rsp+270h+var_210.LowPart], rdi
0x1800b6ca4  lock inc dword ptr [rdi+8]
0x1800b6ca8  lea     rdx, [rsp+270h+var_210]
0x1800b6cad  lea     rcx, [rbp+170h+var_1C0]
0x1800b6cb1  call    ??0CStoredIdentityTransaction@@QEAA@V?$CAutoRefPtr@VCStoredIdentity@@@@@Z; CStoredIdentityTransaction::CStoredIdentityTransaction(CAutoRefPtr<CStoredIdentity>)
0x1800b6cb6  nop
0x1800b6cb7  lea     rcx, [rbp+170h+var_1C0]; this
0x1800b6cbb  call    ?Start@CStoredIdentityTransaction@@QEAAJXZ; CStoredIdentityTransaction::Start(void)
0x1800b6cc0  mov     [rbp+170h+arg_18], eax
0x1800b6cc6  test    eax, eax
  ... truncated ...
```
