# HandleRemovePersistedCredential(void * const,ushort const *,unsigned __int64)

- ea: `0x18009362c`
- end: `0x180093d0c`
- name: `?HandleRemovePersistedCredential@@YAJQEAXPEBG_K@Z`
- size: `1760`
- prototype: `__int64 __fastcall(void *const, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18006da60`
- `0x180093510`
- `0x1800b1afc`

## callees

- `0x18000c050`
- `0x18000cfac`
- `0x18000ed04`
- `0x18000fd04`
- `0x18001426c`
- `0x1800151c4`
- `0x180019690`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f968`
- `0x180020970`
- `0x180020b10`
- `0x18002994c`
- `0x180029d54`
- `0x18002d36c`
- `0x180043344`
- `0x18004cb2c`
- `0x18004d8c4`
- `0x180079554`
- `0x18007c38c`
- `0x18008bbb0`
- `0x18009362c`
- `0x180093e30`
- `0x1800bbd14`
- `0x1800dad38`
- `0x1800daeb0`
- `0x1800db050`
- `0x1800db174`
- `0x1800ef93c`
- `0x1800f1d10`
- `0x1800f2d80`
- `0x180128010`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x1800937c4`
- `ntdll!RtlAcquireResourceShared` at `0x1800937c4`
- `ntdll!RtlReleaseResource` at `0x180093882`
- `ntdll!RtlReleaseResource` at `0x18009389a`
- `ntdll!RtlReleaseResource` at `0x180093882`
- `ntdll!RtlReleaseResource` at `0x18009389a`

## string_xrefs

- `0x1800938c4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18009368a`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800936e4`: `hr = client.ImpersonateClient()`
- `0x180093671`: `HandleRemovePersistedCredential`
- `0x18009385d`: `Cannot delete stored CAW cookie hr=0x%x`
- `0x180093961`: `Cannot delete stored credentials hr=0x%x`
- `0x180093a3f`: `Cannot remove user persisted service tokens hr=0x%x`
- `0x180093aa8`: `Cannot remove user presisted certificates hr=0x%x`
- `0x180093b23`: `Cannot remove user persisted TOTP Shared Key hr=0x%x`
- `0x180093c2a`: `Cannot remove linked user creds hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall HandleRemovePersistedCredential(__int64 a1, unsigned __int16 *a2, char a3)
{
  int v6; // eax
  int LogonId; // eax
  int SingleIdentity; // eax
  struct CSingleIdentity *v9; // rbx
  const unsigned __int16 **v10; // rax
  struct _RTL_RESOURCE *v11; // rdi
  __int64 v12; // rax
  CIdentityTokenBag *v13; // rcx
  int v14; // eax
  int v15; // edi
  __int64 v16; // rdi
  __int64 *v17; // rax
  int v18; // eax
  const unsigned __int16 **v19; // rax
  const unsigned __int16 *v20; // rdx
  unsigned int v21; // edi
  _QWORD *v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  char *v25; // rdi
  unsigned int v26; // esi
  _QWORD *v27; // rax
  _QWORD *v28; // rax
  __int64 v29; // rbx
  __int64 *v30; // rax
  _QWORD *v31; // rax
  __int64 v32; // rbx
  __int64 *v33; // rax
  int v34; // eax
  CSingleIdentity **v35; // rax
  CSingleIdentity **v36; // rax
  unsigned int v37; // ebx
  char *v39; // [rsp+20h] [rbp-E0h]
  struct _LUID v40; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  struct CSingleIdentity *v46[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h] BYREF
  const char *v48[5]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v49[272]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]
  int v51; // [rsp+208h] [rbp+108h] BYREF

  v51 = 0;
  CTraceFuncW<long>::CTraceFuncW<long>(
    v48,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    5984,
    (const char *)&v51,
    "HandleRemovePersistedCredential",
    L"wszCredType='%ls'");
  v40 = 0;
  v46[0] = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  v43 = 0;
  v6 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v43, 0);
  v51 = v6;
  if ( v6 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleRemovePersistedCredential",
      0x176Cu,
      v6,
      "hr = client.ImpersonateClient()");
    goto LABEL_49;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v43, &v40);
  v51 = LogonId;
  if ( LogonId < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleRemovePersistedCredential",
      0x176Du,
      LogonId,
      "hr = client.GetLogonId(logonId)");
    goto LABEL_49;
  }
  SingleIdentity = CIdentityStore::GetSingleIdentity((__int64)g_pPPCRL + 496, &v40, a1, v46);
  v51 = SingleIdentity;
  if ( SingleIdentity < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleRemovePersistedCredential",
      0x176Fu,
      SingleIdentity,
      "hr = g_pPPCRL->GetIdentityStore()->GetSingleIdentity(logonId, handle, pIdentity)");
    goto LABEL_49;
  }
  v9 = v46[0];
  v10 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(struct CSingleIdentity *, __int64 *))(*(_QWORD *)v46[0]
                                                                                                  + 32LL))(
                                     v46[0],
                                     &v44);
  HandleRemoveUserFromSsoGroup(*v10, 2u, 0x20u);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  v11 = (struct _RTL_RESOURCE *)((char *)g_pPPCRL + 2136);
  v46[1] = (CPassportClientLibrary *)((char *)g_pPPCRL + 2136);
  RtlAcquireResourceShared((PRTL_RESOURCE)((char *)g_pPPCRL + 2136), 1u);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v45,
    L"Default");
  WebCookieManager::WebCookieManager((WebCookieManager *)v49);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v44,
    L"CAW");
  v12 = (*(__int64 (__fastcall **)(struct CSingleIdentity *, __int64 *))(*(_QWORD *)v9 + 32LL))(v9, &v41);
  v40 = (struct _LUID)v9;
  if ( v9 )
    _InterlockedIncrement((volatile signed __int32 *)v9 + 2);
  v51 = WebCookieManager::DeleteCookieData(v49, &v40, v12, &v44);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v44);
  if ( v51 < 0 )
  {
    LODWORD(v39) = v51;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x1788u,
      L"Cannot delete stored CAW cookie hr=0x%x",
      v39);
    WebCookieManager::~WebCookieManager((WebCookieManager *)v49);
    RtlReleaseResource(v11);
    goto LABEL_49;
  }
  WebCookieManager::~WebCookieManager((WebCookieManager *)v49);
  RtlReleaseResource(v11);
  if ( (a3 & 4) != 0 )
  {
    v13 = (CIdentityTokenBag *)*((_QWORD *)v9 + 11);
    if ( v13 && (v14 = CIdentityTokenBag::DeleteKeyCache(v13), v15 = v14, v14 < 0) )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x630,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        (const char *)(unsigned int)v14,
        (int)v39);
    else
      v15 = 0;
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1791,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        (const char *)(unsigned int)v15,
        (int)v39);
  }
  if ( *((_DWORD *)v9 + 184) )
  {
    if ( (a3 & 1) == 0 )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x1798u,
        L"Skipping deletion of credentials for connected account.");
      goto LABEL_49;
    }
  }
  else
  {
    v16 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)v9 + 8LL))(v9);
    v17 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v41,
            a2);
    v18 = CIdentityCredentialBag::DeleteStoredCredential(v16, v17);
    v51 = v18;
    if ( v18 < 0 )
    {
      LODWORD(v39) = v18;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x17A3u,
        L"Cannot delete stored credentials hr=0x%x",
        v39);
      goto LABEL_49;
    }
    if ( (a3 & 2) == 0 )
    {
      (*(void (__fastcall **)(struct CSingleIdentity *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v9 + 64LL))(
        v9,
        L"CID",
        &v42);
      if ( *((_DWORD *)v42 - 4) )
      {
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
        ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v49);
        if ( (int)CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v43, &v40) >= 0 )
          RemoveMSAIDPKeyIfSecondaryOrAssociated(
            (struct IServiceExecutionContext *)v49,
            v9,
            v42,
            *(const unsigned __int16 **)&v40,
            0);
        ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v49);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
      }
    }
  }
  v19 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(struct CSingleIdentity *, __int64 *))(*(_QWORD *)v9 + 32LL))(
                                     v9,
                                     &v41);
  v51 = CServiceTokenInfo::RemovePersistedServiceTokens(*v19, v20);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  if ( v51 < 0 )
  {
    LODWORD(v39) = v51;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x17CAu,
      L"Cannot remove user persisted service tokens hr=0x%x",
      v39);
  }
  v21 = (*(__int64 (__fastcall **)(struct CSingleIdentity *))(*(_QWORD *)v9 + 80LL))(v9);
  v22 = (_QWORD *)(*(__int64 (__fastcall **)(struct CSingleIdentity *, __int64 *))(*(_QWORD *)v9 + 32LL))(v9, &v41);
  v51 = CCertificateInfo::RemovePersistedCertificates(*v22, v23, v21);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
  if ( v51 < 0 )
  {
    LODWORD(v39) = v51;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x17D4u,
      L"Cannot remove user presisted certificates hr=0x%x",
      v39);
  }
  if ( (a3 & 1) != 0 )
  {
    if ( (*(int (__fastcall **)(struct CSingleIdentity *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v9 + 64LL))(
           v9,
           L"CID",
           &v42) < 0 )
    {
      LODWORD(v39) = v51;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x17E8u,
        L"CID is not set for the current identity hr=0x%x",
        v39);
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64 *)&v40,
        L"MicrosoftAccount:(TOTPSharedKey):UserPuid=");
      ATL::CSimpleStringT<unsigned short,0>::Append(&v40, &v42);
      v24 = ManageApproverRequest::DeleteTotpKeyFromCache(*(LPCWSTR *)&v40);
      v51 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v39) = v24;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x17E3u,
          L"Cannot remove user persisted TOTP Shared Key hr=0x%x",
          v39);
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v40);
    }
  }
  v25 = (char *)v9 + 568;
  v26 = 0;
  if ( *((_QWORD *)v9 + 72) )
  {
    while ( 1 )
    {
      v27 = (_QWORD *)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                        v25,
                        v26);
      if ( !(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 8LL))(*v27) )
        goto LABEL_44;
      v28 = (_QWORD *)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                        v25,
                        v26);
      v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v28 + 8LL))(*v28);
      v30 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v41,
              L"ps:password");
      if ( !(unsigned __int8)CIdentityCredentialBag::HasPersistedCredential(v29, v30) )
        break;
LABEL_45:
      if ( (unsigned __int64)++v26 >= *((_QWORD *)v25 + 1) )
        goto LABEL_46;
    }
    v31 = (_QWORD *)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                      v25,
                      v26);
    v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 8LL))(*v31);
    v33 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            &v45,
            a2);
    v34 = CIdentityCredentialBag::DeleteStoredCredential(v32, v33);
    v51 = v34;
    if ( v34 < 0 )
    {
      LODWORD(v39) = v34;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x17FDu,
        L"Cannot remove linked user creds hr=0x%x",
        v39);
      v51 = 0;
    }
LABEL_44:
    v35 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                v25,
                                v26);
    CSingleIdentity::RemovePersistedServiceTokens(*v35);
    v36 = (CSingleIdentity **)ATL::CAtlArray<ATL::CAutoPtr<ATL::CDacl::CAccessAce>,ATL::CAutoPtrElementTraits<ATL::CDacl::CAccessAce>>::operator[](
                                v25,
                                v26);
    CSingleIdentity::RemovePersistedCertificates(*v36);
    goto LABEL_45;
  }
LABEL_46:
  if ( v51 < 0 )
  {
    LODWORD(v39) = v51;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x180Au,
      L"Cannot cleare user ext properties hr=0x%x",
      v39);
  }
  v51 = 0;
LABEL_49:
  v37 = v51;
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v43);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v42);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v47);
  CAutoRefPtr<CSingleIdentity>::Deinit(v46);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v48);
  return v37;
}

```

## disassembly

```asm
0x18009362c  mov     [rsp-8+arg_0], rbx
0x180093631  mov     [rsp-8+arg_8], rsi
0x180093636  push    rbp
0x180093637  push    rdi
0x180093638  push    r13
0x18009363a  push    r14
0x18009363c  push    r15
0x18009363e  lea     rbp, [rsp-0C0h]
0x180093646  sub     rsp, 1C0h
0x18009364d  mov     r14, r8
0x180093650  mov     r15, rdx
0x180093653  mov     rbx, rcx
0x180093656  mov     [rbp+0E0h+arg_18], 0
0x180093660  mov     [rsp+1E0h+var_1B0], rdx
0x180093665  lea     rax, aWszcredtypeLs; "wszCredType='%ls'"
0x18009366c  mov     [rsp+1E0h+var_1B8], rax
0x180093671  lea     rdi, aHandleremovepe; "HandleRemovePersistedCredential"
0x180093678  mov     [rsp+1E0h+var_1C0], rdi; int
0x18009367d  lea     r9, [rbp+0E0h+arg_18]
0x180093684  mov     r8d, 1760h
0x18009368a  lea     r13, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180093691  mov     rdx, r13
0x180093694  lea     rcx, [rbp+0E0h+var_158]
0x180093698  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x18009369d  nop
0x18009369e  mov     qword ptr [rsp+1E0h+var_1A0.LowPart], 0
0x1800936a7  mov     [rsp+1E0h+var_170], 0
0x1800936b0  lea     rcx, [rbp+0E0h+var_160]
0x1800936b4  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800936b9  nop
0x1800936ba  lea     rcx, [rsp+1E0h+var_190]
0x1800936bf  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800936c4  nop
0x1800936c5  mov     [rsp+1E0h+var_188], 0
0x1800936ce  xor     edx, edx; struct ATL::CAccessToken *
0x1800936d0  lea     rcx, [rsp+1E0h+var_188]; this
0x1800936d5  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x1800936da  mov     [rbp+0E0h+arg_18], eax
0x1800936e0  test    eax, eax
0x1800936e2  jns     short loc_180093709
0x1800936e4  lea     r8, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x1800936eb  mov     [rsp+1E0h+var_1C0], r8; char *
0x1800936f0  mov     r8d, 176Ch; unsigned int
0x1800936f6  mov     r9d, eax; int
0x1800936f9  mov     rdx, rdi; char *
0x1800936fc  mov     rcx, r13; char *
0x1800936ff  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180093704  jmp     loc_180093CB4
0x180093709  lea     rdx, [rsp+1E0h+var_1A0]; struct _LUID *
0x18009370e  lea     rcx, [rsp+1E0h+var_188]; this
0x180093713  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x180093718  mov     [rbp+0E0h+arg_18], eax
0x18009371e  test    eax, eax
0x180093720  jns     short loc_180093736
0x180093722  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x180093729  mov     [rsp+1E0h+var_1C0], rcx
0x18009372e  mov     r8d, 176Dh
0x180093734  jmp     short loc_1800936F6
0x180093736  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18009373d  add     rcx, 1F0h
0x180093744  lea     r9, [rsp+1E0h+var_170]
0x180093749  mov     r8, rbx
0x18009374c  lea     rdx, [rsp+1E0h+var_1A0]
0x180093751  call    ?GetSingleIdentity@CIdentityStore@@QEAAJAEAU_LUID@@PEAXAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::GetSingleIdentity(_LUID &,void *,CAutoRefPtr<CSingleIdentity> &)
0x180093756  mov     [rbp+0E0h+arg_18], eax
0x18009375c  test    eax, eax
0x18009375e  jns     short loc_180093774
0x180093760  lea     rcx, aHrGPppcrlGetid_29; "hr = g_pPPCRL->GetIdentityStore()->GetS"...
0x180093767  mov     [rsp+1E0h+var_1C0], rcx
0x18009376c  mov     r8d, 176Fh
0x180093772  jmp     short loc_1800936F6
0x180093774  mov     rbx, [rsp+1E0h+var_170]
0x180093779  mov     rax, [rbx]
0x18009377c  lea     rdx, [rsp+1E0h+var_180]
0x180093781  mov     rcx, rbx
0x180093784  mov     rax, [rax+20h]
0x180093788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009378d  nop
0x18009378e  mov     esi, 2
0x180093793  lea     r8d, [rsi+1Eh]; unsigned int
0x180093797  mov     edx, esi; unsigned __int64
0x180093799  mov     rcx, [rax]; unsigned __int16 *
0x18009379c  call    ?HandleRemoveUserFromSsoGroup@@YAJPEBG_KK@Z; HandleRemoveUserFromSsoGroup(ushort const *,unsigned __int64,ulong)
0x1800937a1  nop
0x1800937a2  lea     rcx, [rsp+1E0h+var_180]
0x1800937a7  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800937ac  mov     rdi, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800937b3  add     rdi, 858h
0x1800937ba  mov     [rsp+1E0h+var_168], rdi
0x1800937bf  mov     dl, 1; Wait
0x1800937c1  mov     rcx, rdi; Resource
0x1800937c4  call    cs:__imp_RtlAcquireResourceShared
0x1800937ca  nop
0x1800937cb  lea     rdx, aDefault; "Default"
0x1800937d2  lea     rcx, [rsp+1E0h+var_178]
0x1800937d7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800937dc  mov     rdx, rax
0x1800937df  lea     rcx, [rbp+0E0h+var_130]; this
0x1800937e3  call    ??0WebCookieManager@@QEAA@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebCookieManager::WebCookieManager(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x1800937e8  nop
0x1800937e9  lea     rdx, aCaw; "CAW"
0x1800937f0  lea     rcx, [rsp+1E0h+var_180]
0x1800937f5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800937fa  nop
0x1800937fb  mov     rax, [rbx]
0x1800937fe  lea     rdx, [rsp+1E0h+var_198]
0x180093803  mov     rcx, rbx
0x180093806  mov     rax, [rax+20h]
0x18009380a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009380f  nop
0x180093810  mov     qword ptr [rsp+1E0h+var_1A0.LowPart], rbx
0x180093815  test    rbx, rbx
0x180093818  jz      short loc_18009381E
0x18009381a  lock inc dword ptr [rbx+8]
0x18009381e  lea     r9, [rsp+1E0h+var_180]
0x180093823  mov     r8, rax
0x180093826  lea     rdx, [rsp+1E0h+var_1A0]
0x18009382b  lea     rcx, [rbp+0E0h+var_130]
0x18009382f  call    ?DeleteCookieData@WebCookieManager@@QEAAJV?$CAutoRefPtr@VCSingleIdentity@@@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1@Z; WebCookieManager::DeleteCookieData(CAutoRefPtr<CSingleIdentity>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180093834  mov     [rbp+0E0h+arg_18], eax
0x18009383a  lea     rcx, [rsp+1E0h+var_198]
0x18009383f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180093844  nop
0x180093845  lea     rcx, [rsp+1E0h+var_180]
0x18009384a  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18009384f  mov     eax, [rbp+0E0h+arg_18]
0x180093855  test    eax, eax
0x180093857  jns     short loc_18009388D
0x180093859  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x18009385d  lea     r9, aCannotDeleteSt; "Cannot delete stored CAW cookie hr=0x%x"
0x180093864  mov     r8d, 1788h; unsigned int
0x18009386a  mov     rdx, r13; char *
0x18009386d  mov     ecx, esi; unsigned __int8
0x18009386f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180093874  nop
0x180093875  lea     rcx, [rbp+0E0h+var_130]; this
0x180093879  call    ??1WebCookieManager@@QEAA@XZ; WebCookieManager::~WebCookieManager(void)
0x18009387e  nop
0x18009387f  mov     rcx, rdi; Resource
0x180093882  call    cs:__imp_RtlReleaseResource
0x180093888  jmp     loc_180093CB4
0x18009388d  lea     rcx, [rbp+0E0h+var_130]; this
0x180093891  call    ??1WebCookieManager@@QEAA@XZ; WebCookieManager::~WebCookieManager(void)
0x180093896  nop
0x180093897  mov     rcx, rdi; Resource
0x18009389a  call    cs:__imp_RtlReleaseResource
0x1800938a0  test    r14b, 4
0x1800938a4  jz      short loc_1800938F4
0x1800938a6  mov     rcx, [rbx+58h]; this
0x1800938aa  test    rcx, rcx
0x1800938ad  jz      short loc_1800938D7
0x1800938af  call    ?DeleteKeyCache@CIdentityTokenBag@@QEAAJXZ; CIdentityTokenBag::DeleteKeyCache(void)
0x1800938b4  mov     edi, eax
0x1800938b6  test    eax, eax
0x1800938b8  jns     short loc_1800938D7
0x1800938ba  mov     rcx, [rbp+0E8h]; this
0x1800938c1  mov     r9d, eax; char *
0x1800938c4  lea     r8, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800938cb  mov     edx, 630h; void *
0x1800938d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800938d5  jmp     short loc_1800938D9
0x1800938d7  xor     edi, edi
0x1800938d9  mov     rcx, [rbp+0E8h]; this
0x1800938e0  test    edi, edi
0x1800938e2  jns     short loc_1800938F4
0x1800938e4  mov     r9d, edi; char *
0x1800938e7  mov     r8, r13; unsigned int
0x1800938ea  mov     edx, 1791h; void *
0x1800938ef  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800938f4  mov     rsi, r14
0x1800938f7  and     esi, 1
0x1800938fa  cmp     dword ptr [rbx+2E0h], 0
0x180093901  jz      short loc_180093929
0x180093903  test    rsi, rsi
0x180093906  jnz     loc_180093A04
0x18009390c  lea     r9, aSkippingDeleti; "Skipping deletion of credentials for co"...
0x180093913  mov     r8d, 1798h; unsigned int
0x180093919  mov     rdx, r13; char *
0x18009391c  lea     ecx, [rsi+5]; unsigned __int8
0x18009391f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180093924  jmp     loc_180093CB4
0x180093929  mov     rax, [rbx]
0x18009392c  mov     rcx, rbx
0x18009392f  mov     rax, [rax+8]
0x180093933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093938  mov     rdi, rax
0x18009393b  mov     rdx, r15
0x18009393e  lea     rcx, [rsp+1E0h+var_198]
0x180093943  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180093948  mov     rdx, rax
0x18009394b  mov     rcx, rdi
0x18009394e  call    ?DeleteStoredCredential@CIdentityCredentialBag@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CIdentityCredentialBag::DeleteStoredCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180093953  mov     [rbp+0E0h+arg_18], eax
0x180093959  test    eax, eax
0x18009395b  jns     short loc_180093980
0x18009395d  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180093961  lea     r9, aCannotDeleteSt_0; "Cannot delete stored credentials hr=0x%"...
0x180093968  mov     r8d, 17A3h; unsigned int
0x18009396e  mov     rdx, r13; char *
0x180093971  mov     ecx, 2; unsigned __int8
0x180093976  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18009397b  jmp     loc_180093CB4
0x180093980  test    r14b, 2
0x180093984  jnz     short loc_180093A04
0x180093986  mov     rax, [rbx]
0x180093989  lea     r8, [rsp+1E0h+var_190]
0x18009398e  lea     rdx, aCid; "CID"
0x180093995  mov     rcx, rbx
0x180093998  mov     rax, [rax+40h]
0x18009399c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939a1  mov     rax, [rsp+1E0h+var_190]
0x1800939a6  cmp     dword ptr [rax-10h], 0
0x1800939aa  jz      short loc_180093A04
0x1800939ac  lea     rcx, [rsp+1E0h+var_1A0]
0x1800939b1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800939b6  nop
0x1800939b7  lea     rcx, [rbp+0E0h+var_130]; this
0x1800939bb  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800939c0  nop
0x1800939c1  lea     rdx, [rsp+1E0h+var_1A0]
0x1800939c6  lea     rcx, [rsp+1E0h+var_188]; this
0x1800939cb  call    ?GetTokenUser@CAutoImpersonateClient@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAutoImpersonateClient::GetTokenUser(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800939d0  test    eax, eax
0x1800939d2  js      short loc_1800939F0
0x1800939d4  mov     byte ptr [rsp+1E0h+var_1C0], 0; bool
0x1800939d9  mov     r9, qword ptr [rsp+1E0h+var_1A0.LowPart]; unsigned __int16 *
0x1800939de  mov     r8, [rsp+1E0h+var_190]; unsigned __int16 *
0x1800939e3  mov     rdx, rbx; struct CSingleIdentity *
0x1800939e6  lea     rcx, [rbp+0E0h+var_130]; struct IServiceExecutionContext *
0x1800939ea  call    ?RemoveMSAIDPKeyIfSecondaryOrAssociated@@YAJPEAVIServiceExecutionContext@@PEAVCSingleIdentity@@PEBG2_N@Z; RemoveMSAIDPKeyIfSecondaryOrAssociated(IServiceExecutionContext *,CSingleIdentity *,ushort const *,ushort const *,bool)
0x1800939ef  nop
0x1800939f0  lea     rcx, [rbp+0E0h+var_130]; this
0x1800939f4  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x1800939f9  nop
0x1800939fa  lea     rcx, [rsp+1E0h+var_1A0]
0x1800939ff  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180093a04  mov     rax, [rbx]
0x180093a07  lea     rdx, [rsp+1E0h+var_198]
0x180093a0c  mov     rcx, rbx
0x180093a0f  mov     rax, [rax+20h]
0x180093a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a18  nop
0x180093a19  mov     rcx, [rax]; unsigned __int16 *
0x180093a1c  call    ?RemovePersistedServiceTokens@CServiceTokenInfo@@SAJPEBG0@Z; CServiceTokenInfo::RemovePersistedServiceTokens(ushort const *,ushort const *)
0x180093a21  mov     [rbp+0E0h+arg_18], eax
0x180093a27  lea     rcx, [rsp+1E0h+var_198]
0x180093a2c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180093a31  mov     eax, [rbp+0E0h+arg_18]
0x180093a37  test    eax, eax
0x180093a39  jns     short loc_180093A59
0x180093a3b  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180093a3f  lea     r9, aCannotRemoveUs_1; "Cannot remove user persisted service to"...
0x180093a46  mov     r8d, 17CAh; unsigned int
0x180093a4c  mov     rdx, r13; char *
0x180093a4f  mov     ecx, 2; unsigned __int8
0x180093a54  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180093a59  mov     rax, [rbx]
0x180093a5c  mov     rcx, rbx
0x180093a5f  mov     rax, [rax+50h]
0x180093a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a68  mov     edi, eax
0x180093a6a  mov     rcx, [rbx]
0x180093a6d  mov     rax, [rcx+20h]
0x180093a71  lea     rdx, [rsp+1E0h+var_198]
0x180093a76  mov     rcx, rbx
0x180093a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a7e  nop
0x180093a7f  mov     r8d, edi
0x180093a82  mov     rcx, [rax]
0x180093a85  call    ?RemovePersistedCertificates@CCertificateInfo@@SAJPEBG0W4PPCRLUserType@@@Z; CCertificateInfo::RemovePersistedCertificates(ushort const *,ushort const *,PPCRLUserType)
0x180093a8a  mov     [rbp+0E0h+arg_18], eax
0x180093a90  lea     rcx, [rsp+1E0h+var_198]
0x180093a95  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180093a9a  mov     eax, [rbp+0E0h+arg_18]
0x180093aa0  test    eax, eax
0x180093aa2  jns     short loc_180093AC2
0x180093aa4  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x180093aa8  lea     r9, aCannotRemoveUs_0; "Cannot remove user presisted certificat"...
0x180093aaf  mov     r8d, 17D4h; unsigned int
0x180093ab5  mov     rdx, r13; char *
0x180093ab8  mov     ecx, 2; unsigned __int8
0x180093abd  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180093ac2  test    rsi, rsi
0x180093ac5  jz      loc_180093B6E
0x180093acb  mov     rax, [rbx]
0x180093ace  lea     r8, [rsp+1E0h+var_190]
0x180093ad3  lea     rdx, aCid; "CID"
0x180093ada  mov     rcx, rbx
0x180093add  mov     rax, [rax+40h]
0x180093ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ae6  test    eax, eax
0x180093ae8  js      short loc_180093B4A
0x180093aea  lea     rdx, aMicrosoftaccou_1; "MicrosoftAccount:(TOTPSharedKey):UserPu"...
0x180093af1  lea     rcx, [rsp+1E0h+var_1A0]
0x180093af6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180093afb  nop
0x180093afc  lea     rdx, [rsp+1E0h+var_190]
0x180093b01  lea     rcx, [rsp+1E0h+var_1A0]
0x180093b06  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x180093b0b  mov     rcx, qword ptr [rsp+1E0h+var_1A0.LowPart]; TargetName
  ... truncated ...
```
