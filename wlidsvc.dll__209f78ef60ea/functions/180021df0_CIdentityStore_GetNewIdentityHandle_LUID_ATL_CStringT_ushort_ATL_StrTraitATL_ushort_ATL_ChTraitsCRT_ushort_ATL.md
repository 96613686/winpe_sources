# CIdentityStore::GetNewIdentityHandle(_LUID &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CAccessToken &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,unsigned __int64,void * *)

- ea: `0x180021df0`
- end: `0x180022dac`
- name: `?GetNewIdentityHandle@CIdentityStore@@QEAAJAEAU_LUID@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVCAccessToken@4@KV34@_KPEAPEAX@Z`
- size: `4028`
- prototype: `__int64 __fastcall(__int64, struct _LUID *, LPCWSTR *, ATL::CAccessToken *, int, _QWORD *, __int64, _QWORD *)`
- caller_count: `4`
- callee_count: `76`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800216f8`
- `0x18008cf4c`
- `0x1800bc9a0`
- `0x1800be4e0`

## callees

- `0x18000c050`
- `0x18000e71c`
- `0x18000ecb0`
- `0x18000ed04`
- `0x18000ed3c`
- `0x18000fa30`
- `0x18000fd04`
- `0x180010fb8`
- `0x1800124c4`
- `0x180013448`
- `0x1800151c4`
- `0x180015860`
- `0x180018f80`
- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001cf20`
- `0x18001d050`
- `0x18001e5d0`
- `0x18001ec18`
- `0x18001f968`
- `0x180021b28`
- `0x180021bbc`
- `0x180021c10`
- `0x180021c80`
- `0x180021d7c`
- `0x180021df0`
- `0x1800231bc`
- `0x180029d54`
- `0x18002d36c`
- `0x180030a8c`
- `0x180035050`
- `0x1800396e8`
- `0x180039d60`
- `0x180039f2c`
- `0x18003b044`
- `0x18003c5c8`
- `0x18003c814`
- `0x18003ee14`
- `0x180043344`
- `0x180046f34`
- `0x180048764`
- `0x18004a878`
- `0x18004e128`
- `0x180050740`
- `0x180051320`
- `0x180053620`
- `0x180053d08`
- `0x180054140`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180021fb0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180021fb0`
- `USERENV!LoadUserProfileW` at `0x180022a9a`
- `USERENV!LoadUserProfileW` at `0x180022a9a`

## string_xrefs

- `0x180021f2f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180021f73`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180021fde`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x1800222b7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x18002244f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x1800224f4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x1800227c7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x18002293d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x18002298f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x1800229d2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180022a52`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180022aab`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180022ba1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180022d85`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\identitystore.cpp`
- `0x180022cee`: `RetrievePersistedServiceTokens: failed hr = 0x%x, trying to continue`
- `0x180022c44`: `CAuthInfo::GetCachedAuthInfo failed with hr = 0x%x, trying to continue`
- `0x180021f0c`: `LogonId.LowPart='%d, LogonId.HighPart='%d, pszSid=%ls, wstrIdentityName=%ls, flags=0x%llx`
- `0x180021fc5`: `ConvertStringSidToSid(pszSid, &spSid) != FALSE`
- `0x18002219d`: `hr = CreateNewIdentity(hIdentity)`
- `0x1800223f9`: `hr = CreateNewIdentity(hIdentity)`
- `0x180022369`: `!pszSid.IsEmpty()`
- `0x180022433`: `hr = IsAuthDisabledByEnterpriseDeviceAuthPolicy(&serviceExecutionContext, hIdentity)`
- `0x1800227ba`: `Created new identity 0x%p.`
- `0x180022c90`: `hr = hIdentity->GetTokenBag()->CacheAndEncryptPersistedPassword(wstrPassword)`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
__int64 __fastcall CIdentityStore::GetNewIdentityHandle(
        __int64 a1,
        struct _LUID *a2,
        LPCWSTR *a3,
        ATL::CAccessToken *a4,
        int a5,
        _QWORD *a6,
        __int64 a7,
        _QWORD *a8)
{
  _BYTE *v11; // rsi
  __int64 v12; // rax
  int v13; // r13d
  unsigned __int8 v14; // dl
  PPTraceStatus *v15; // rcx
  char v16; // cl
  const unsigned __int16 *String; // rax
  int v18; // r9d
  unsigned int v19; // r8d
  const unsigned __int16 *v20; // r8
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  int DeviceIdInternal; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  int v27; // eax
  const char *v28; // rcx
  unsigned int v29; // r8d
  CSingleIdentity *v30; // rdi
  int v31; // r14d
  char v32; // al
  __int64 v33; // rsi
  __int64 v34; // rax
  int v35; // eax
  const char *v36; // rcx
  unsigned int v37; // r8d
  __int64 v38; // rsi
  __int64 v39; // rax
  unsigned __int16 *v40; // rsi
  LPCWSTR v41; // rax
  int v42; // eax
  const char *v43; // rcx
  unsigned int v44; // r8d
  int IdentityProperty; // eax
  int v46; // eax
  bool v47; // zf
  __int64 v48; // r9
  int ExtProperty; // eax
  unsigned __int16 *v50; // r8
  int v51; // eax
  __int64 v52; // r9
  int v53; // eax
  __int64 v54; // r13
  __int64 v55; // r11
  struct _LUID *v56; // r14
  __int64 v57; // rax
  struct CIdentityTokenBag *v58; // rbx
  __int64 v59; // rbx
  __int64 v60; // rbx
  unsigned int LastError; // ebx
  int v63; // eax
  int TokenSid; // eax
  __int64 v65; // rcx
  WCHAR *v66; // rax
  int v67; // eax
  const char *v68; // r9
  __int64 v69; // r8
  __int64 Node; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  int v73; // eax
  const char *v74; // rcx
  unsigned int v75; // r8d
  int PersistedServiceTokens; // eax
  int PersistedCertificates; // eax
  char *v78; // [rsp+20h] [rbp-E0h]
  char *v79; // [rsp+20h] [rbp-E0h]
  char *v80; // [rsp+20h] [rbp-E0h]
  char *v81; // [rsp+20h] [rbp-E0h]
  __int64 v82; // [rsp+28h] [rbp-D8h]
  int IsDefaultIdentity; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v84; // [rsp+68h] [rbp-98h] BYREF
  bool v85; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v86; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *Src; // [rsp+80h] [rbp-80h] BYREF
  __int64 v88; // [rsp+88h] [rbp-78h] BYREF
  BYTE pbBuffer[8]; // [rsp+90h] [rbp-70h] BYREF
  PSID Sid[3]; // [rsp+98h] [rbp-68h] BYREF
  char v91[8]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v92; // [rsp+B8h] [rbp-48h] BYREF
  CSingleIdentity *v93; // [rsp+C0h] [rbp-40h] BYREF
  struct _LUID *v94; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v95; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v96; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE *v97; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v98; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v99; // [rsp+F0h] [rbp-10h] BYREF
  struct CIdentityTokenBag *v100; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v101; // [rsp+100h] [rbp+0h] BYREF
  __int64 v102; // [rsp+108h] [rbp+8h] BYREF
  void **v103; // [rsp+110h] [rbp+10h] BYREF
  HANDLE hToken[2]; // [rsp+118h] [rbp+18h]
  __int64 v105; // [rsp+128h] [rbp+28h]
  _QWORD *v106; // [rsp+130h] [rbp+30h]
  _QWORD *v107; // [rsp+138h] [rbp+38h]
  unsigned __int16 **v108; // [rsp+140h] [rbp+40h]
  _PROFILEINFOW ProfileInfo; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v110[3]; // [rsp+180h] [rbp+80h] BYREF
  char v111; // [rsp+198h] [rbp+98h]
  _QWORD *v112; // [rsp+1A0h] [rbp+A0h]
  _BYTE v113[40]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v114[88]; // [rsp+1D0h] [rbp+D0h] BYREF
  WCHAR *v115; // [rsp+228h] [rbp+128h]
  _QWORD v116[42]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+458h] [rbp+358h]

  v94 = a2;
  v95 = a1;
  v107 = a6;
  v112 = a6;
  v106 = a8;
  v11 = 0;
  IsDefaultIdentity = 0;
  *(_QWORD *)pbBuffer = 0;
  v93 = 0;
  v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Trim(a6);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &Src,
    v12);
  v99 = 0;
  v13 = 0;
  LODWORD(v88) = 0;
  LODWORD(v86) = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v101);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v98);
  v97 = 0;
  v96 = 0;
  if ( !PPTraceShouldRedact() || (LOBYTE(v15) = 1, !PPTraceStatus::TraceOnFlag(v15, v14)) )
    v16 = 0;
  v110[1] = *a6;
  v110[2] = 0;
  v111 = v16;
  v110[0] = &PPRedactedStringW::`vftable';
  String = PPRedactedStringW::GetString((PPRedactedStringW *)v110);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v113,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
    445,
    &IsDefaultIdentity,
    "CIdentityStore::GetNewIdentityHandle",
    L"LogonId.LowPart='%d, LogonId.HighPart='%d, pszSid=%ls, wstrIdentityName=%ls, flags=0x%llx",
    a2->LowPart,
    a2->HighPart,
    *a3,
    String,
    a7);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v110);
  if ( !a8 )
  {
    v18 = -2147467261;
    IsDefaultIdentity = -2147467261;
    v79 = "phandle != nullptr";
    v19 = 448;
LABEL_6:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
      "CIdentityStore::GetNewIdentityHandle",
      v19,
      v18,
      v79);
    goto LABEL_134;
  }
  *a8 = 0;
  v102 = a7 & 0x400000;
  if ( (a7 & 0x400000) != 0 )
  {
    memset(Sid, 0, sizeof(Sid));
    if ( !ConvertStringSidToSidW(*a3, Sid) )
    {
      IsDefaultIdentity = -2147024809;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        "CIdentityStore::GetNewIdentityHandle",
        0x1C7u,
        -2147024809,
        "ConvertStringSidToSid(pszSid, &spSid) != FALSE");
      Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(Sid);
      goto LABEL_134;
    }
    Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(Sid);
  }
  v21 = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
  v22 = v21;
  v92 = v21;
  if ( (a7 & 0x20000) != 0 )
  {
    if ( v21 )
    {
      *v21 = 0;
      v21[1] = 0;
      v21[2] = &ATL::CAccessToken::`vftable';
      v21[3] = 0;
      v21[4] = 0;
      v21[5] = 0;
      *((_DWORD *)v21 + 12) = a5;
      *((_BYTE *)v21 + 52) = 1;
      v21[7] = 0;
    }
    else
    {
      v22 = 0;
    }
    *((_BYTE *)v22 + 52) = 0;
  }
  else if ( v21 )
  {
    *v21 = 0;
    v21[1] = 0;
    v21[2] = &ATL::CAccessToken::`vftable';
    v21[3] = 0;
    v21[4] = 0;
    v21[5] = 0;
    *((_DWORD *)v21 + 12) = a5;
    *((_BYTE *)v21 + 52) = 1;
    v21[7] = 0;
    v21[3] = ATL::CAccessToken::Detach(a4);
  }
  else
  {
    v22 = 0;
  }
  v99 = v22;
  if ( !v22 )
  {
LABEL_89:
    IsDefaultIdentity = -2147024882;
    goto LABEL_90;
  }
  if ( (a7 & 0x100000) != 0 )
  {
    CAutoRefPtr<CSingleIdentity>::Deinit(&v97);
    DeviceIdInternal = GetDeviceIdInternal(L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}", 0, 0, 0, (__int64)&v97);
    IsDefaultIdentity = DeviceIdInternal;
    if ( DeviceIdInternal < 0 )
    {
      v79 = "hr = GetDeviceIdInternal( g_szStrongAuthAppId, 0, 0, &wszDeviceId, nullptr, nullptr, &pDeviceIdentity)";
      v18 = DeviceIdInternal;
      v19 = 481;
      goto LABEL_6;
    }
    v11 = v97;
  }
  LOBYTE(v20) = 1;
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(Sid, v95, v20);
  v24 = 0;
  if ( (a7 & 0x100000) != 0 )
  {
    if ( !v96 )
    {
      IsDefaultIdentity = -2147188658;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        "CIdentityStore::GetNewIdentityHandle",
        0x1ECu,
        -2147188658,
        "wszDeviceId != nullptr");
LABEL_133:
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(Sid);
      goto LABEL_134;
    }
    v25 = (*(__int64 (__fastcall **)(_BYTE *, unsigned __int16 **))(*(_QWORD *)v11 + 32LL))(v11, &v84);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&Src, v25);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
    v27 = CIdentityStore::CreateNewIdentity(v26, &v93);
    IsDefaultIdentity = v27;
    if ( v27 < 0 )
    {
      v28 = "hr = CreateNewIdentity(hIdentity)";
      v29 = 497;
LABEL_132:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        "CIdentityStore::GetNewIdentityHandle",
        v29,
        v27,
        v28);
      goto LABEL_133;
    }
    v30 = v93;
    *((_DWORD *)v93 + 66) = 1;
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v30 + 720, L"{fc177c6f-a3d6-4bb0-b1fa-23d0cd9b005d}");
    v85 = (unsigned int)CSingleIdentity::IsCredentialBagEmpty(v30) != 0;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v84,
      &Src);
    v27 = CSingleIdentity::SetIdentityName(v30);
    IsDefaultIdentity = v27;
    v31 = 0;
    if ( v27 < 0 )
    {
      v28 = "hr = hIdentity->SetIdentityName( LogonId, wstrUsername )";
      v29 = 507;
      goto LABEL_132;
    }
    v27 = CSingleIdentity::SetPUID(v30, v96);
    IsDefaultIdentity = v27;
    if ( v27 < 0 )
    {
      v28 = "hr = hIdentity->SetPUID(wszDeviceId)";
      v29 = 508;
      goto LABEL_132;
    }
    v32 = v11[626];
    *((_BYTE *)v30 + 626) = v32;
    if ( !v32 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
      v33 = (*(__int64 (__fastcall **)(_BYTE *))(*(_QWORD *)v11 + 8LL))(v11);
      v34 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v86,
              L"ps:password");
      v35 = CIdentityCredentialBag::RetrieveCredential(v33, v34, &v84, 0);
      IsDefaultIdentity = v35;
      if ( v35 < 0 )
      {
        v36 = "hr = pDeviceIdentity->GetCredBag()->RetrieveCredential( PPCRL_CREDTYPE_PASSWORD, wszPassword )";
        v37 = 514;
LABEL_36:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
          "CIdentityStore::GetNewIdentityHandle",
          v37,
          v35,
          v36);
        CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v84);
        goto LABEL_133;
      }
      v38 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v30 + 8LL))(v30);
      v108 = &v86;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v86,
        &v84);
      v39 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v92,
              L"ps:password");
      v35 = CIdentityCredentialBag::StoreCredential(v38, v39, &v86);
      IsDefaultIdentity = v35;
      if ( v35 < 0 )
      {
        v36 = "hr = hIdentity->GetCredBag()->StoreCredential( PPCRL_CREDTYPE_PASSWORD, wszPassword )";
        v37 = 515;
        goto LABEL_36;
      }
      CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v84);
    }
    v40 = Src;
    goto LABEL_79;
  }
  v40 = Src;
  v41 = *a3;
  if ( *((_DWORD *)Src - 4) )
  {
    if ( !*((_DWORD *)v41 - 4) )
      goto LABEL_50;
    IsDefaultIdentity = CSystemStore::IsDefaultIdentity(a3, &Src, &v86);
    v13 = (int)v86;
  }
  else
  {
    if ( !*((_DWORD *)v41 - 4) )
    {
      IsDefaultIdentity = -2147024809;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        "CIdentityStore::GetNewIdentityHandle",
        0x20Eu,
        -2147024809,
        "!pszSid.IsEmpty()");
      goto LABEL_133;
    }
    IsDefaultIdentity = CSystemStore::GetDefaultIdentity(a3, a2, &Src);
    if ( IsDefaultIdentity )
    {
      IsDefaultIdentity = -2147188724;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        "CIdentityStore::GetNewIdentityHandle",
        0x213u,
        -2147188724,
        "hr == S_OK");
      goto LABEL_133;
    }
    v13 = 1;
    v40 = Src;
  }
  LODWORD(v88) = v13;
LABEL_50:
  v27 = CIdentityStore::CreateNewIdentity(v24, &v93);
  IsDefaultIdentity = v27;
  if ( v27 < 0 )
  {
    v28 = "hr = CreateNewIdentity(hIdentity)";
    v29 = 543;
    goto LABEL_132;
  }
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v114);
  v30 = v93;
  v42 = IsAuthDisabledByEnterpriseDeviceAuthPolicy((struct IServiceExecutionContext *)v114, v93);
  IsDefaultIdentity = v42;
  if ( v42 < 0 )
  {
    v43 = "hr = IsAuthDisabledByEnterpriseDeviceAuthPolicy(&serviceExecutionContext, hIdentity)";
    v44 = 546;
LABEL_54:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
      "CIdentityStore::GetNewIdentityHandle",
      v44,
      v42,
      v43);
    ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v114);
    goto LABEL_133;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v92,
    &Src);
  v42 = CSingleIdentity::SetIdentityName(v30);
  IsDefaultIdentity = v42;
  v31 = 0;
  if ( v42 < 0 )
  {
    v43 = "hr = hIdentity->SetIdentityName(LogonId, wstrUsername)";
    v44 = 548;
    goto LABEL_54;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString((char *)v30 + 720, L"{83928489-55ae-4c23-94ec-03a106b80ba2}");
  if ( (unsigned int)CSingleIdentity::IsCredentialBagEmpty(v30) || (v85 = 0, v13) )
    v85 = 1;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
  IdentityProperty = CSystemStore::GetIdentityProperty(&Src, L"CID", &v84);
  IsDefaultIdentity = IdentityProperty;
  if ( IdentityProperty < 0 )
  {
    LODWORD(v78) = IdentityProperty;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
      0x237u,
      L"GetIdentityProperty failed. Ignoring the failure. hr=0x%x",
      v78);
    IsDefaultIdentity = CUserExtendedProperty::GetExtProperty(v40);
    if ( IsDefaultIdentity < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Empty(&v84);
      LODWORD(v78) = IsDefaultIdentity;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        0x23Eu,
        L"CUserExtendedProperty::GetExtProperty failed. Ignoring the failure. hr=0x%x",
        v78);
    }
  }
  if ( *((_DWORD *)v84 - 4) )
  {
    v46 = CSingleIdentity::SetCredProperty(v30, L"CID", v84);
    IsDefaultIdentity = v46;
    if ( v46 < 0 )
    {
      LODWORD(v78) = v46;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        0x248u,
        L"SetCredProperty(CID) failed. Ignoring the failure. hr=0x%x",
        v78);
    }
  }
  IsDefaultIdentity = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v86,
    L"PUID");
  IsDefaultIdentity = CSystemStore::GetIdentityProperty(&Src, v86, &v84);
  v47 = (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v30 + 80LL))(v30) == 0;
  ExtProperty = IsDefaultIdentity;
  if ( !v47 )
    goto LABEL_70;
  if ( IsDefaultIdentity < 0 || (v50 = v84, !*((_DWORD *)v84 - 4)) )
  {
    LOBYTE(v48) = 1;
    ExtProperty = CSingleIdentity::GetExtProperty(v30, &v86, &v84, v48);
    IsDefaultIdentity = ExtProperty;
LABEL_70:
    v50 = v84;
  }
  if ( ExtProperty >= 0 && *((_DWORD *)v50 - 4) )
  {
    v51 = CSingleIdentity::SetCredProperty(v30, v86, v50);
    IsDefaultIdentity = v51;
    if ( v51 < 0 )
    {
      LODWORD(v78) = v51;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        0x25Eu,
        L"SetCredProperty(PUID) failed. Ignoring the failure. hr=0x%x",
        v78);
    }
    if ( !(*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v30 + 80LL))(v30) )
    {
      LOBYTE(v52) = 1;
      v53 = CSingleIdentity::SetExtProperty(v30, &v86, &v84, v52);
      IsDefaultIdentity = v53;
      if ( v53 < 0 )
      {
        LODWORD(v78) = v53;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
          0x266u,
          L"SetExtProperty(PUID) failed. Ignoring the failure. hr=0x%x",
          v78);
      }
    }
  }
  IsDefaultIdentity = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v84);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v114);
  while ( 1 )
  {
LABEL_79:
    v27 = CCryptRandom::GenRandom((LPCRITICAL_SECTION)g_cryptRandom, pbBuffer, 8u);
    IsDefaultIdentity = v27;
    if ( v27 < 0 )
    {
      v28 = "hr = GenRandomNumber(reinterpret_cast<LPBYTE>(&handle), static_cast<DWORD>(sizeof(handle)))";
      v29 = 624;
      goto LABEL_132;
    }
    v54 = v95 + 40;
    LODWORD(v84) = 0;
    LODWORD(v86) = 0;
    if ( !ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::GetNode(
            (int)v95 + 40,
            *(_DWORD *)pbBuffer,
            (unsigned int)&v84,
            (unsigned int)&v86,
            (__int64)&v100) )
    {
      if ( v55 )
        break;
    }
    if ( (unsigned int)++v31 >= 0x400 )
    {
      IsDefaultIdentity = -2147418113;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        "CIdentityStore::GetNewIdentityHandle",
        0x273u,
        -2147418113,
        "dwRetries < PPCRL_MAX_HANDLE_RETRIES");
      goto LABEL_133;
    }
  }
  CAutoRefPtr<CSingleIdentity>::operator=(v22);
  v56 = v94;
  v22[1] = *v94;
  v57 = ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::operator[](
          v54,
          *(_QWORD *)pbBuffer);
  ATL::CAutoPtr<CWLIDContext>::operator=(v57, &v99);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
    0x279u,
    L"Created new identity 0x%p.");
  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(Sid);
  if ( v102 )
    CSingleIdentity::SetCallerSidOverwrite(v30, a3);
  if ( (a7 & 0x10000) == 0 )
  {
    *((_DWORD *)v30 + 184) = v88;
    if ( (a7 & 0x80000) != 0 )
    {
      *((_BYTE *)v30 + 268) = 1;
      v58 = (struct CIdentityTokenBag *)operator new(0x1F0u);
      v100 = v58;
      (*(void (__fastcall **)(CSingleIdentity *, __int64 *))(*(_QWORD *)v30 + 32LL))(v30, &v102);
      v59 = CIdentityTokenBag::CIdentityTokenBag(v58);
      CAutoRefPtr<IStoredIdentity>::Deinit((char *)v30 + 96);
      *((_QWORD *)v30 + 12) = v59;
      if ( !v59 )
        goto LABEL_89;
      v56 = v94;
    }
    else if ( (a7 & 0x8000) != 0 )
    {
      *((_BYTE *)v30 + 269) = 1;
    }
    if ( (a7 & 0x800000000LL) != 0 )
    {
      v103 = &ATL::CAccessToken::`vftable';
      *(_OWORD *)hToken = 0;
      v105 = 0;
      v88 = 0;
      v63 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v88, (struct ATL::CAccessToken *)&v103);
      LastError = v63;
      if ( v63 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29A,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
          (const char *)(unsigned int)v63,
          (int)v30);
LABEL_110:
        CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v88);
        v103 = &ATL::CAccessToken::`vftable';
        ATL::CAccessToken::Clear((ATL::CAccessToken *)&v103);
        goto LABEL_93;
      }
      ATL::CSid::CSid((ATL::CSid *)v114);
      TokenSid = CAutoImpersonateClient::GetTokenSid((CAutoImpersonateClient *)&v88, (struct ATL::CSid *)v114);
      LastError = TokenSid;
      if ( TokenSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29D,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
          (const char *)(unsigned int)TokenSid,
          (int)v30);
LABEL_109:
        ATL::CSid::~CSid((ATL::CSid *)v114);
        goto LABEL_110;
      }
      memset(&ProfileInfo, 0, sizeof(ProfileInfo));
      ProfileInfo.dwSize = 56;
      v66 = v115;
      if ( !*((_DWORD *)v115 - 4) )
      {
        ATL::CSid::GetAccountNameAndDomain((ATL::CSid *)v114);
        v66 = v115;
      }
      ProfileInfo.lpUserName = v66;
      ProfileInfo.dwFlags = 17;
      v84 = (unsigned __int16 *)-1LL;
      v67 = wil::impersonate_token_nothrow(v65, &v84);
      LastError = v67;
      if ( v67 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A7,
          (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
          (const char *)(unsigned int)v67,
          (int)v30);
LABEL_108:
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v84);
        goto LABEL_109;
      }
      wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
        v116,
        "UserProfileLoad");
      v116[0] = &MSAClientTraceTelemetry::UserProfileLoad::`vftable';
      MSAClientTraceTelemetry::UserProfileLoad::StartActivity((MSAClientTraceTelemetry::UserProfileLoad *)v116);
      if ( !LoadUserProfileW(hToken[0], &ProfileInfo) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2A9,
                      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
                      v68);
        MSAClientTraceTelemetry::UserProfileLoad::~UserProfileLoad((MSAClientTraceTelemetry::UserProfileLoad *)v116);
        goto LABEL_108;
      }
      MSAClientTraceTelemetry::UserProfileLoad::Stop(
        (MSAClientTraceTelemetry::UserProfileLoad *)v116,
        ProfileInfo.hProfile);
      MSAClientTraceTelemetry::UserProfileLoad::~UserProfileLoad((MSAClientTraceTelemetry::UserProfileLoad *)v116);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v84);
      LOBYTE(v69) = 1;
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(Sid, v95, v69);
      LODWORD(v86) = 0;
      LODWORD(v84) = 0;
      Node = ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::GetNode(
               v54,
               *(_DWORD *)pbBuffer,
               (unsigned int)&v86,
               (unsigned int)&v84,
               (__int64)&v100);
      v71 = *(_QWORD *)(Node + 8);
      *(_QWORD *)(Node + 8) = 0;
      v94 = (struct _LUID *)v71;
      *(_QWORD *)(v71 + 56) = ProfileInfo.hProfile;
      LODWORD(v82) = v56->LowPart;
      LODWORD(v80) = v56->HighPart;
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        0x2B3u,
        L"LUID=[%d,%d] LoadUserProfile %p",
        v80,
        v82,
        ProfileInfo.hProfile);
      v72 = ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::operator[](
              v54,
              *(_QWORD *)pbBuffer);
      ATL::CAutoPtr<CWLIDContext>::operator=(v72, &v94);
      ATL::CAutoPtr<CWLIDContext>::Free(&v94);
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(Sid);
      ATL::CSid::~CSid((ATL::CSid *)v114);
      CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v88);
      v103 = &ATL::CAccessToken::`vftable';
      ATL::CAccessToken::Clear((ATL::CAccessToken *)&v103);
    }
    IsDefaultIdentity = CAuthInfo::GetCachedAuthInfo(v40, (__int64)&v101, (__int64)v91);
    if ( IsDefaultIdentity < 0 )
    {
      if ( !*((_DWORD *)v40 - 4) )
        CSingleIdentity::CheckDefaultCredential();
      LODWORD(v81) = IsDefaultIdentity;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
        0x2C6u,
        L"CAuthInfo::GetCachedAuthInfo failed with hr = 0x%x, trying to continue",
        v81);
      IsDefaultIdentity = 0;
    }
    if ( v85 )
    {
      if ( *(_DWORD *)(v98 - 16) )
      {
        v73 = CIdentityTokenBag::CacheAndEncryptPersistedPassword(*((_QWORD *)v30 + 11), &v98);
        IsDefaultIdentity = v73;
        if ( v73 < 0 )
        {
          v74 = "hr = hIdentity->GetTokenBag()->CacheAndEncryptPersistedPassword(wstrPassword)";
          v75 = 720;
LABEL_120:
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
            "CIdentityStore::GetNewIdentityHandle",
            v75,
            v73,
            v74);
          goto LABEL_134;
        }
      }
      if ( *((_DWORD *)v101 - 4) )
      {
        v73 = CSingleIdentity::ImportAuthState(v30, v56, v20, v101);
        IsDefaultIdentity = v73;
        if ( v73 == -2147186552 )
        {
          IsDefaultIdentity = 0;
        }
        else if ( v73 < 0 )
        {
          v74 = "hr";
          v75 = 733;
          goto LABEL_120;
        }
      }
      PersistedServiceTokens = CSingleIdentity::RetrievePersistedServiceTokens(v30);
      IsDefaultIdentity = PersistedServiceTokens;
      if ( PersistedServiceTokens < 0 )
      {
        LODWORD(v81) = PersistedServiceTokens;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
          0x2E5u,
          L"RetrievePersistedServiceTokens: failed hr = 0x%x, trying to continue",
          v81);
        IsDefaultIdentity = 0;
      }
      PersistedCertificates = CSingleIdentity::RetrievePersistedCertificates(v30);
      IsDefaultIdentity = PersistedCertificates;
      if ( PersistedCertificates < 0 )
      {
        LODWORD(v81) = PersistedCertificates;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\identitystore.cpp",
          0x2EEu,
          L"RetrievePersistedCertificates: failed hr = 0x%x, trying to continue",
          v81);
        IsDefaultIdentity = 0;
      }
    }
  }
  *v106 = *(_QWORD *)pbBuffer;
LABEL_134:
  if ( IsDefaultIdentity < 0 )
  {
LABEL_90:
    if ( *(_QWORD *)pbBuffer )
    {
      LOBYTE(v20) = 1;
      v60 = v95;
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(Sid, v95, v20);
      ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::RemoveKey(
        v60 + 40,
        *(_QWORD *)pbBuffer);
      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(Sid);
    }
  }
  LastError = IsDefaultIdentity;
LABEL_93:
  CTraceFuncW<long>::~CTraceFuncW<long>(v113);
  CPassportStringW::~CPassportStringW((CPassportStringW *)&v96);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v97);
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v98);
  CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v101);
  ATL::CAutoPtr<CWLIDContext>::Free(&v99);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Src);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v93);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v107);
  return LastError;
}

```

## disassembly

```asm
0x180021df0  push    rbp
0x180021df2  push    rbx
0x180021df3  push    rsi
0x180021df4  push    rdi
0x180021df5  push    r12
0x180021df7  push    r13
0x180021df9  push    r14
0x180021dfb  push    r15
0x180021dfd  lea     rbp, [rsp-318h]
0x180021e05  sub     rsp, 418h
0x180021e0c  mov     rax, cs:__security_cookie
0x180021e13  xor     rax, rsp
0x180021e16  mov     [rbp+350h+var_50], rax
0x180021e1d  mov     rdi, r9
0x180021e20  mov     r12, r8
0x180021e23  mov     r14, rdx
0x180021e26  mov     [rbp+350h+var_388], rdx
0x180021e2a  mov     [rbp+350h+var_380], rcx
0x180021e2e  mov     r15, [rbp+350h+arg_28]
0x180021e35  mov     [rbp+350h+var_318], r15
0x180021e39  mov     [rbp+350h+var_2B0], r15
0x180021e40  mov     rbx, [rbp+350h+arg_38]
0x180021e47  mov     [rbp+350h+var_320], rbx
0x180021e4b  xor     esi, esi
0x180021e4d  mov     [rsp+450h+var_3F0], esi
0x180021e51  mov     qword ptr [rbp+350h+pbBuffer], rsi
0x180021e55  mov     [rbp+350h+var_390], rsi
0x180021e59  mov     rcx, r15
0x180021e5c  call    ?Trim@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Trim(void)
0x180021e61  mov     rdx, rax
0x180021e64  lea     rcx, [rbp+350h+Src]
0x180021e68  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180021e6d  nop
0x180021e6e  mov     [rbp+350h+var_360], rsi
0x180021e72  mov     r13d, esi
0x180021e75  mov     dword ptr [rbp+350h+var_3C8], esi
0x180021e78  mov     dword ptr [rsp+450h+var_3D8], esi
0x180021e7c  lea     rcx, [rbp+350h+var_350]
0x180021e80  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180021e85  nop
0x180021e86  lea     rcx, [rbp+350h+var_368]
0x180021e8a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180021e8f  nop
0x180021e90  mov     [rbp+350h+var_370], rsi
0x180021e94  mov     [rbp+350h+var_378], rsi
0x180021e98  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180021e9d  test    al, al
0x180021e9f  jz      short loc_180021EAC
0x180021ea1  mov     cl, 1; this
0x180021ea3  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180021ea8  test    al, al
0x180021eaa  jnz     short loc_180021EAE
0x180021eac  xor     cl, cl
0x180021eae  mov     rax, [r15]
0x180021eb1  mov     [rbp+350h+var_2C8], rax
0x180021eb8  mov     [rbp+350h+var_2C0], 0
0x180021ec3  mov     [rbp+350h+var_2B8], cl
0x180021ec9  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180021ed0  mov     [rbp+350h+var_2D0], rax
0x180021ed7  lea     rcx, [rbp+350h+var_2D0]; this
0x180021ede  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180021ee3  mov     r15, [rbp+350h+arg_30]
0x180021eea  mov     [rsp+450h+var_400], r15
0x180021eef  mov     [rsp+450h+var_408], rax
0x180021ef4  mov     rax, [r12]
0x180021ef8  mov     [rsp+450h+var_410], rax
0x180021efd  mov     eax, [r14+4]
0x180021f01  mov     [rsp+450h+var_418], eax
0x180021f05  mov     eax, [r14]
0x180021f08  mov     dword ptr [rsp+450h+var_420], eax
0x180021f0c  lea     rax, aLogonidLowpart_1; "LogonId.LowPart='%d, LogonId.HighPart='"...
0x180021f13  mov     [rsp+450h+var_428], rax
0x180021f18  lea     rax, aCidentitystore_11; "CIdentityStore::GetNewIdentityHandle"
0x180021f1f  mov     [rsp+450h+var_430], rax
0x180021f24  lea     r9, [rsp+450h+var_3F0]
0x180021f29  mov     r8d, 1BDh
0x180021f2f  lea     rdx, aOnecoreuapDsEx_92; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180021f36  lea     rcx, [rbp+350h+var_2A8]
0x180021f3d  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180021f42  nop
0x180021f43  lea     rcx, [rbp+350h+var_2D0]; this
0x180021f4a  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180021f4f  xor     ecx, ecx
0x180021f51  test    rbx, rbx
0x180021f54  jnz     short loc_180021F8B
0x180021f56  mov     r9d, 80004003h; int
0x180021f5c  mov     [rsp+450h+var_3F0], r9d
0x180021f61  lea     rax, aPhandleNullptr; "phandle != nullptr"
0x180021f68  mov     [rsp+450h+var_430], rax; char *
0x180021f6d  mov     r8d, 1C0h; unsigned int
0x180021f73  lea     rcx, aOnecoreuapDsEx_92; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180021f7a  lea     rdx, aCidentitystore_11; "CIdentityStore::GetNewIdentityHandle"
0x180021f81  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180021f86  jmp     loc_180022D9B
0x180021f8b  mov     [rbx], rcx
0x180021f8e  mov     rax, r15
0x180021f91  and     eax, 400000h
0x180021f96  mov     [rbp+350h+var_348], rax
0x180021f9a  jz      short loc_180022001
0x180021f9c  mov     [rbp+350h+Sid], rcx
0x180021fa0  mov     [rbp+350h+var_3A8], rcx
0x180021fa4  mov     [rbp+350h+var_3B0], rcx
0x180021fa8  lea     rdx, [rbp+350h+Sid]; Sid
0x180021fac  mov     rcx, [r12]; StringSid
0x180021fb0  call    cs:__imp_ConvertStringSidToSidW
0x180021fb6  test    eax, eax
0x180021fb8  jnz     short loc_180021FF8
0x180021fba  mov     r9d, 80070057h; int
0x180021fc0  mov     [rsp+450h+var_3F0], r9d
0x180021fc5  lea     rax, aConvertstrings_1; "ConvertStringSidToSid(pszSid, &spSid) !"...
0x180021fcc  mov     [rsp+450h+var_430], rax; char *
0x180021fd1  mov     r8d, 1C7h; unsigned int
0x180021fd7  lea     rdx, aCidentitystore_11; "CIdentityStore::GetNewIdentityHandle"
0x180021fde  lea     rcx, aOnecoreuapDsEx_92; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180021fe5  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180021fea  lea     rcx, [rbp+350h+Sid]
0x180021fee  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180021ff3  jmp     loc_180022D9B
0x180021ff8  lea     rcx, [rbp+350h+Sid]
0x180021ffc  call    ??1?$Auto@PEAU_NGC_USER_ID_KEY_INFO@@V?$LocalAllocFunctor@PEAU_NGC_USER_ID_KEY_INFO@@@@VDummyContext@@@@QEAA@XZ; Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>::~Auto<_NGC_USER_ID_KEY_INFO *,LocalAllocFunctor<_NGC_USER_ID_KEY_INFO *>,DummyContext>(void)
0x180022001  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022008  mov     ecx, 40h ; '@'; unsigned __int64
0x18002200d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180022012  mov     rbx, rax
0x180022015  lea     rcx, ??_7CAccessToken@ATL@@6B@; const ATL::CAccessToken::`vftable'
0x18002201c  xor     edx, edx
0x18002201e  mov     [rbp+350h+var_398], rax
0x180022022  bt      r15, 11h
0x180022027  jnb     short loc_180022062
0x180022029  test    rax, rax
0x18002202c  jz      short loc_18002205A
0x18002202e  mov     [rax], rdx
0x180022031  xor     eax, eax
0x180022033  mov     [rbx+8], rax
0x180022037  mov     [rbx+10h], rcx
0x18002203b  mov     [rbx+18h], rdx
0x18002203f  mov     [rbx+20h], rdx
0x180022043  mov     [rbx+28h], rdx
0x180022047  mov     eax, [rbp+350h+arg_20]
0x18002204d  mov     [rbx+30h], eax
0x180022050  mov     byte ptr [rbx+34h], 1
0x180022054  mov     [rbx+38h], rdx
0x180022058  jmp     short loc_18002205D
0x18002205a  mov     rbx, rdx
0x18002205d  mov     [rbx+34h], dl
0x180022060  jmp     short loc_1800220A2
0x180022062  test    rax, rax
0x180022065  jz      short loc_18002209F
0x180022067  mov     [rax], rdx
0x18002206a  xor     eax, eax
0x18002206c  mov     [rbx+8], rax
0x180022070  mov     [rbx+10h], rcx
0x180022074  mov     [rbx+18h], rdx
0x180022078  mov     [rbx+20h], rdx
0x18002207c  mov     [rbx+28h], rdx
0x180022080  mov     eax, [rbp+350h+arg_20]
0x180022086  mov     [rbx+30h], eax
0x180022089  mov     byte ptr [rbx+34h], 1
0x18002208d  mov     [rbx+38h], rdx
0x180022091  mov     rcx, rdi; this
0x180022094  call    ?Detach@CAccessToken@ATL@@QEAAPEAXXZ; ATL::CAccessToken::Detach(void)
0x180022099  mov     [rbx+18h], rax
0x18002209d  jmp     short loc_1800220A2
0x18002209f  mov     rbx, rdx
0x1800220a2  mov     rax, rbx
0x1800220a5  mov     [rbp+350h+var_360], rbx
0x1800220a9  test    rax, rax
0x1800220ac  jz      loc_18002286C
0x1800220b2  mov     rdi, r15
0x1800220b5  and     edi, 100000h
0x1800220bb  jz      short loc_18002211C
0x1800220bd  lea     rcx, [rbp+350h+var_370]
0x1800220c1  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x1800220c6  lea     rax, [rbp+350h+var_370]
0x1800220ca  mov     [rsp+450h+var_420], rax
0x1800220cf  mov     [rsp+450h+var_428], 0
0x1800220d8  mov     [rsp+450h+var_430], 0
0x1800220e1  lea     r9, [rbp+350h+var_378]
0x1800220e5  xor     r8d, r8d
0x1800220e8  xor     edx, edx
0x1800220ea  lea     rcx, aAfda72bf340941; "{AFDA72BF-3409-413a-B54E-2AB8D66A7826}"
0x1800220f1  call    ?GetDeviceIdInternal@@YAJPEBG_K1PEAPEAGPEAPEBU_CERT_CONTEXT@@PEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEAPEAVCSingleIdentity@@@Z; GetDeviceIdInternal(ushort const *,unsigned __int64,unsigned __int64,ushort * *,_CERT_CONTEXT const * *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> *,CSingleIdentity * *)
0x1800220f6  mov     [rsp+450h+var_3F0], eax
0x1800220fa  test    eax, eax
0x1800220fc  jns     short loc_180022118
0x1800220fe  lea     rcx, aHrGetdeviceidi_0; "hr = GetDeviceIdInternal( g_szStrongAut"...
0x180022105  mov     [rsp+450h+var_430], rcx
0x18002210a  mov     r9d, eax
0x18002210d  mov     r8d, 1E1h
0x180022113  jmp     loc_180021F73
0x180022118  mov     rsi, [rbp+350h+var_370]
0x18002211c  mov     r8b, 1
0x18002211f  mov     rdx, [rbp+350h+var_380]
0x180022123  lea     rcx, [rbp+350h+Sid]
0x180022127  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18002212c  nop
0x18002212d  xor     ecx, ecx
0x18002212f  test    rdi, rdi
0x180022132  jz      loc_18002234C
0x180022138  cmp     [rbp+350h+var_378], rcx
0x18002213c  jnz     short loc_180022160
0x18002213e  mov     r9d, 8004804Eh
0x180022144  mov     [rsp+450h+var_3F0], r9d
0x180022149  lea     rax, aWszdeviceidNul; "wszDeviceId != nullptr"
0x180022150  mov     [rsp+450h+var_430], rax
0x180022155  mov     r8d, 1ECh
0x18002215b  jmp     loc_180022D7E
0x180022160  mov     rax, [rsi]
0x180022163  lea     rdx, [rsp+450h+var_3E8]
0x180022168  mov     rcx, rsi
0x18002216b  mov     rax, [rax+20h]
0x18002216f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022174  nop
0x180022175  mov     rdx, rax
0x180022178  lea     rcx, [rbp+350h+Src]
0x18002217c  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180022181  nop
0x180022182  lea     rcx, [rsp+450h+var_3E8]
0x180022187  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002218c  lea     rdx, [rbp+350h+var_390]
0x180022190  call    ?CreateNewIdentity@CIdentityStore@@QEAAJAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::CreateNewIdentity(CAutoRefPtr<CSingleIdentity> &)
0x180022195  mov     [rsp+450h+var_3F0], eax
0x180022199  test    eax, eax
0x18002219b  jns     short loc_1800221AF
0x18002219d  lea     rcx, aHrCreatenewide; "hr = CreateNewIdentity(hIdentity)"
0x1800221a4  mov     r8d, 1F1h
0x1800221aa  jmp     loc_180022D76
0x1800221af  mov     rdi, [rbp+350h+var_390]
0x1800221b3  mov     dword ptr [rdi+108h], 1
0x1800221bd  lea     rcx, [rdi+2D0h]
0x1800221c4  lea     rdx, aFc177c6fA3d64b; "{fc177c6f-a3d6-4bb0-b1fa-23d0cd9b005d}"
0x1800221cb  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800221d0  mov     rcx, rdi; this
0x1800221d3  call    ?IsCredentialBagEmpty@CSingleIdentity@@QEAAHXZ; CSingleIdentity::IsCredentialBagEmpty(void)
0x1800221d8  test    eax, eax
0x1800221da  setnz   [rsp+450h+var_3E0]
0x1800221df  lea     rdx, [rbp+350h+Src]
0x1800221e3  lea     rcx, [rsp+450h+var_3E8]
0x1800221e8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800221ed  mov     r8, rax
0x1800221f0  mov     rdx, r14
0x1800221f3  mov     rcx, rdi; this
0x1800221f6  call    ?SetIdentityName@CSingleIdentity@@QEAAJAEAU_LUID@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CSingleIdentity::SetIdentityName(_LUID &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x1800221fb  mov     [rsp+450h+var_3F0], eax
0x1800221ff  xor     r14d, r14d
0x180022202  test    eax, eax
0x180022204  jns     short loc_180022218
0x180022206  lea     rcx, aHrHidentitySet_0; "hr = hIdentity->SetIdentityName( LogonI"...
0x18002220d  mov     r8d, 1FBh
0x180022213  jmp     loc_180022D76
0x180022218  mov     rdx, [rbp+350h+var_378]; unsigned __int16 *
0x18002221c  mov     rcx, rdi; this
0x18002221f  call    ?SetPUID@CSingleIdentity@@QEAAJPEBG@Z; CSingleIdentity::SetPUID(ushort const *)
0x180022224  mov     [rsp+450h+var_3F0], eax
0x180022228  test    eax, eax
0x18002222a  jns     short loc_18002223E
0x18002222c  lea     rcx, aHrHidentitySet; "hr = hIdentity->SetPUID(wszDeviceId)"
0x180022233  mov     r8d, 1FCh
0x180022239  jmp     loc_180022D76
0x18002223e  mov     al, [rsi+272h]
0x180022244  mov     [rdi+272h], al
0x18002224a  test    al, al
0x18002224c  jnz     loc_180022343
0x180022252  lea     rcx, [rsp+450h+var_3E8]
0x180022257  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18002225c  nop
0x18002225d  mov     rax, [rsi]
0x180022260  mov     rcx, rsi
0x180022263  mov     rax, [rax+8]
0x180022267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002226c  mov     rsi, rax
0x18002226f  lea     rdx, aPsPassword_0; "ps:password"
0x180022276  lea     rcx, [rsp+450h+var_3D8]
0x18002227b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022280  xor     r9d, r9d
0x180022283  lea     r8, [rsp+450h+var_3E8]
0x180022288  mov     rdx, rax
0x18002228b  mov     rcx, rsi
0x18002228e  call    ?RetrieveCredential@CIdentityCredentialBag@@QEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@H@Z; CIdentityCredentialBag::RetrieveCredential(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,int)
0x180022293  mov     [rsp+450h+var_3F0], eax
0x180022297  test    eax, eax
0x180022299  jns     short loc_1800222D3
0x18002229b  lea     rcx, aHrPdeviceident_0; "hr = pDeviceIdentity->GetCredBag()->Ret"...
0x1800222a2  mov     r8d, 202h; unsigned int
0x1800222a8  mov     r9d, eax; int
0x1800222ab  mov     [rsp+450h+var_430], rcx; char *
0x1800222b0  lea     rdx, aCidentitystore_11; "CIdentityStore::GetNewIdentityHandle"
0x1800222b7  lea     rcx, aOnecoreuapDsEx_92; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800222be  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800222c3  nop
0x1800222c4  lea     rcx, [rsp+450h+var_3E8]
0x1800222c9  call    ??1?$CAutoZeroMemoryStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CAutoZeroMemoryStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800222ce  jmp     loc_180022D92
0x1800222d3  mov     rax, [rdi]
0x1800222d6  mov     rcx, rdi
0x1800222d9  mov     rax, [rax+8]
0x1800222dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222e2  mov     rsi, rax
0x1800222e5  lea     rax, [rsp+450h+var_3D8]
0x1800222ea  mov     [rbp+350h+var_310], rax
  ... truncated ...
```
