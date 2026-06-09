# CAuthInfo::WriteToCache(ushort const *,ushort const *,bool,bool,ushort const *,ushort const *)

- ea: `0x180068ba0`
- end: `0x180069419`
- name: `?WriteToCache@CAuthInfo@@SAJPEBG0_N100@Z`
- size: `2169`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *Src@<rcx>, const unsigned __int16 *@<rdx>, bool@<r8b>, bool@<r9b>, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `36`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180045af8`
- `0x1800bd8c0`
- `0x180101ed0`

## callees

- `0x180005ee4`
- `0x18000a354`
- `0x18000c050`
- `0x18000db2c`
- `0x18000ed04`
- `0x180013fb4`
- `0x1800143a4`
- `0x1800151c4`
- `0x180015430`
- `0x180015860`
- `0x180016450`
- `0x180017bf0`
- `0x180019690`
- `0x180019780`
- `0x18001a530`
- `0x18001a9c0`
- `0x18001bd78`
- `0x180021b28`
- `0x180021bbc`
- `0x1800268d0`
- `0x180029d54`
- `0x180030120`
- `0x1800396e8`
- `0x180039b00`
- `0x18004d988`
- `0x180050d4c`
- `0x180064e40`
- `0x18006558c`
- `0x180068ba0`
- `0x180079554`
- `0x1800a3b60`
- `0x1800a400c`
- `0x1800a4718`
- `0x1800a4778`
- `0x1800a6650`
- `0x1800d625c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068d72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068d87`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068d72`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180068d87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800692fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800692fd`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_OverrideTokenPersistence` at `0x18006903c`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_OverrideTokenPersistence` at `0x18006903c`

## string_xrefs

- `0x180068cce`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068e2e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068f30`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068fac`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x1800690b8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18006918c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180069226`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180069333`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18006935d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x180068cab`: `wszUserName=%ls, wszVirtualAppName=%ls, wszAuthTokenBlob=%ls`
- `0x180068cb7`: `CAuthInfo::WriteToCache`
- `0x180068f29`: `CAuthInfo::WriteToCache`
- `0x180068fa5`: `CAuthInfo::WriteToCache`
- `0x1800690b1`: `CAuthInfo::WriteToCache`
- `0x180069185`: `CAuthInfo::WriteToCache`
- `0x18006921f`: `CAuthInfo::WriteToCache`
- `0x18006932c`: `CAuthInfo::WriteToCache`
- `0x180069356`: `CAuthInfo::WriteToCache`
- `0x180068f98`: `cbTokenLen <= CRED_MAX_ATTRIBUTES * CRED_MAX_VALUE_SIZE`
- `0x180068f14`: `hr = EncryptCredentialsInSystemContext(&executionContext, strTokenBlob.GetBuffer(), strTokenBlob.GetLength() * sizeof(char), credsOut)`
- `0x180069341`: `hr = StringCchCopyW(pKeyword, cbKeyword, (LPCWSTR)wstrSampleKeyword)`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CAuthInfo::WriteToCache(
        unsigned __int16 *Src,
        const unsigned __int16 *a2,
        char a3,
        char a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  unsigned int v9; // r13d
  unsigned __int8 v10; // dl
  PPTraceStatus *v11; // rcx
  bool v12; // zf
  char v13; // cl
  char v14; // al
  const unsigned __int16 *String; // rsi
  unsigned __int8 v16; // dl
  PPTraceStatus *v17; // rcx
  char v18; // cl
  const unsigned __int16 *v19; // rax
  __int64 v20; // r15
  unsigned __int64 v21; // rax
  const char *v22; // rax
  unsigned int v23; // r8d
  bool v24; // r12
  unsigned __int64 v25; // rax
  unsigned __int8 v26; // dl
  PPTraceStatus *v27; // rcx
  char v28; // cl
  char v29; // al
  WCHAR *v30; // rsi
  const unsigned __int16 *v31; // rax
  __int64 v32; // rax
  unsigned __int64 v33; // rbx
  __int64 Buffer; // rax
  int v35; // eax
  int v36; // r9d
  unsigned int v37; // edx
  void *v38; // rbx
  unsigned __int16 *v39; // rdi
  DWORD v40; // r14d
  _WORD *v41; // rsi
  int v42; // eax
  void *v43; // rcx
  unsigned __int16 *v44; // rsi
  WCHAR *v45; // rax
  unsigned __int16 *v46; // rcx
  unsigned __int16 *v47; // r12
  __int64 v48; // rsi
  unsigned int v49; // r15d
  __int64 v50; // rax
  int v51; // eax
  int v52; // eax
  __int64 v53; // r10
  signed int LastError; // eax
  unsigned int v55; // ebx
  int v57; // [rsp+50h] [rbp-B0h] BYREF
  char v58; // [rsp+54h] [rbp-ACh]
  char v59; // [rsp+55h] [rbp-ABh]
  unsigned __int16 *v60[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v61; // [rsp+68h] [rbp-98h]
  char v62; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v63; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v64; // [rsp+80h] [rbp-80h]
  WCHAR *v65; // [rsp+88h] [rbp-78h]
  __int64 v66; // [rsp+90h] [rbp-70h]
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v68; // [rsp+A0h] [rbp-60h] BYREF
  void **v69; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v70; // [rsp+B0h] [rbp-50h]
  __int64 v71; // [rsp+B8h] [rbp-48h]
  char v72; // [rsp+C0h] [rbp-40h]
  __int128 v73; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v74; // [rsp+D8h] [rbp-28h]
  char v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v77[4]; // [rsp+F0h] [rbp-10h] BYREF
  struct _CREDENTIALW Credential; // [rsp+110h] [rbp+10h] BYREF
  const char *v79[4]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v80[224]; // [rsp+180h] [rbp+80h] BYREF
  void *Block; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v82[136]; // [rsp+268h] [rbp+168h] BYREF

  v59 = a4;
  v58 = a3;
  v65 = Src;
  v64 = (unsigned __int64)a5;
  v9 = 0;
  v57 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
  memset(v77, 0, 24);
  if ( !PPTraceShouldRedact() || (LOBYTE(v11) = 1, v12 = !PPTraceStatus::TraceOnFlag(v11, v10), v14 = v13, v12) )
    v14 = 0;
  *(_QWORD *)&v73 = &PPRedactedStringW::`vftable';
  *((_QWORD *)&v73 + 1) = a6;
  v74 = 0;
  v75 = v14;
  String = PPRedactedStringW::GetString((PPRedactedStringW *)&v73);
  if ( !PPTraceShouldRedact() || (LOBYTE(v17) = 1, !PPTraceStatus::TraceOnFlag(v17, v16)) )
    v18 = 0;
  v70 = Src;
  v71 = 0;
  v72 = v18;
  v69 = &PPRedactedStringW::`vftable';
  v19 = PPRedactedStringW::GetString((PPRedactedStringW *)&v69);
  CTraceFuncW<long>::CTraceFuncW<long>(
    v79,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    3879,
    (const char *)&v57,
    "CAuthInfo::WriteToCache",
    L"wszUserName=%ls, wszVirtualAppName=%ls, wszAuthTokenBlob=%ls",
    v19,
    a2,
    String);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v69);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)&v73);
  if ( !Src || !*Src )
    goto LABEL_77;
  if ( a3 )
  {
    if ( a2 && *a2 )
    {
      v20 = -1;
      v21 = -1;
      do
        ++v21;
      while ( a2[v21] );
      if ( v21 > 0x100 )
      {
        v22 = "virtAppNameCharLen <= PPCRL_MAX_VIRTUALAPPLEN";
        v23 = 3892;
LABEL_78:
        v36 = -2147024809;
        goto LABEL_79;
      }
      CAuthInfo::GetVirtualAppTargetName(a2, &v68);
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v67, a2);
      v24 = !(unsigned int)_o__wcsicmp(v67, L"DIDSystem") || !(unsigned int)_o__wcsicmp(v67, L"DIDLogical");
      goto LABEL_25;
    }
LABEL_77:
    v22 = "parametersValid";
    v23 = 3887;
    goto LABEL_78;
  }
  v20 = -1;
  v25 = -1;
  do
    ++v25;
  while ( Src[v25] );
  if ( v25 > 0x100 )
  {
    v22 = "userNameCharLen <= PPCRL_MAX_IDLEN";
    v23 = 3905;
    goto LABEL_78;
  }
  v24 = 0;
  CAuthInfo::GetUserTargetName(Src);
LABEL_25:
  v66 = 0;
  if ( !PPTraceShouldRedact() || (LOBYTE(v27) = 1, v12 = !PPTraceStatus::TraceOnFlag(v27, v26), v29 = v28, v12) )
    v29 = 0;
  v60[0] = (unsigned __int16 *)&PPRedactedStringW::`vftable';
  v30 = v68;
  v60[1] = v68;
  v61 = 0;
  v62 = v29;
  v31 = PPRedactedStringW::GetString((PPRedactedStringW *)v60);
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    0xF46u,
    L"wstrTargetName=%ls",
    v31);
  PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v60);
  if ( !a6 || !*a6 )
    goto LABEL_36;
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v80);
  v73 = 0;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
  Block = v82;
  ATL::CW2AEX<128>::Init(&Block, a6, 65001);
  v32 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
          &v63,
          Block);
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(v60, v32);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v63);
  if ( Block != v82 )
    free(Block);
  v33 = *((int *)v60[0] - 4);
  Buffer = ATL::CSimpleStringT<char,0>::GetBuffer(v60);
  v35 = CAuthInfo::EncryptCredentialsInSystemContext<char *>((__int64)v80, Buffer, v33, (__int64)&v73);
  v57 = v35;
  if ( v35 >= 0 )
  {
    Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(v77);
    v66 = *((_QWORD *)&v73 + 1);
    v77[0] = *((_QWORD *)&v73 + 1);
    v9 = v73;
    CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)v60);
    ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v80);
    if ( v9 > 0x4000 )
    {
      v36 = -2147186554;
      v22 = "cbTokenLen <= CRED_MAX_ATTRIBUTES * CRED_MAX_VALUE_SIZE";
      v23 = 3928;
LABEL_79:
      v57 = v36;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CAuthInfo::WriteToCache",
        v23,
        v36,
        v22);
      goto LABEL_80;
    }
LABEL_36:
    memset_0(&Credential, 0, sizeof(Credential));
    v38 = 0;
    *(_QWORD *)&v73 = 0;
    v69 = 0;
    v71 = 0;
    v70 = 0;
    v39 = 0;
    v63 = 0;
    v40 = 0;
    if ( v9 )
      v40 = (v9 + 255) >> 8;
    Credential.Type = 1;
    Credential.TargetName = v30;
    if ( !v58 || v24 )
    {
      Credential.Persist = 2;
      Credential.UserName = v65;
      if ( v24 && (unsigned __int8)IsMsaDevice_FreeDeviceAuthXTokenPresent() )
        MsaDevice_OverrideTokenPersistence(&Credential.Persist);
    }
    else
    {
      Credential.Persist = 1;
      Credential.UserName = v65;
    }
    v41 = (_WORD *)v64;
    if ( v64 && *(_WORD *)v64 )
    {
      ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v80);
      *(_OWORD *)v60 = 0;
      do
        ++v20;
      while ( v41[v20] );
      v42 = CAuthInfo::EncryptCredentialsInSystemContext<unsigned short *>(
              (__int64)v80,
              (__int64)v41,
              2 * v20,
              (__int64)v60);
      v57 = v42;
      if ( v42 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          "CAuthInfo::WriteToCache",
          0xF81u,
          v42,
          "hr = EncryptCredentialsInSystemContext(&executionContext, const_cast<PWSTR>(wszPassword), wcslen(wszPassword)*"
          "sizeof(wchar_t), credsOut)");
        ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v80);
        operator delete(0);
        Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&v69);
        v43 = 0;
LABEL_50:
        operator delete(v43);
        goto LABEL_80;
      }
      Credential.CredentialBlobSize = (DWORD)v60[0];
      v44 = v60[1];
      Credential.CredentialBlob = (LPBYTE)v60[1];
      Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(&v69);
      v69 = (void **)v44;
      ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v80);
      v41 = (_WORD *)v64;
    }
    if ( v59 == 1 || v41 && *v41 )
      v45 = (WCHAR *)L"PersistedCredential";
    else
      v45 = L"MemberNameOnly";
    Credential.Comment = v45;
    if ( v40 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CREDENTIAL_ATTRIBUTEW>::Allocate(&v73, v40) )
      {
        v57 = -2147024882;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          "CAuthInfo::WriteToCache",
          0xF9Cu,
          -2147024882,
          "pAttri.Allocate(cbAttris)");
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
        v46 = 0;
LABEL_60:
        operator delete(v46);
        Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&v69);
        v43 = (void *)v73;
        goto LABEL_50;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(v60, L"Microsoft_WindowsLive:authstate:");
      ATL::CSimpleStringT<unsigned short,0>::Append(v60, L"000");
      LODWORD(v64) = *((_DWORD *)v60[0] - 4);
      if ( !(unsigned __int8)ATL::CAutoVectorPtr<unsigned short>::Allocate(&v63, v40 * (unsigned int)v64) )
      {
        v57 = -2147024882;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
          "CAuthInfo::WriteToCache",
          0xFA2u,
          -2147024882,
          "pAttriKeywords.Allocate(cbAttris * cbKeyword)");
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
        v46 = v63;
        goto LABEL_60;
      }
      v39 = v63;
      v47 = v63;
      Credential.AttributeCount = v40;
      v38 = (void *)v73;
      Credential.Attributes = (PCREDENTIAL_ATTRIBUTEW)v73;
      v48 = v73;
      v49 = 0;
      v50 = v66;
      while ( 1 )
      {
        *(_DWORD *)(v48 + 8) = 0;
        *(_QWORD *)(v48 + 16) = v50;
        v51 = v9;
        if ( v9 >= 0x100 )
          v51 = 256;
        LODWORD(v65) = v51;
        *(_DWORD *)(v48 + 12) = v51;
        *(_QWORD *)v48 = v47;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          v60,
          L"%s%-d",
          L"Microsoft_WindowsLive:authstate:",
          v49);
        v52 = StringCchCopyW(v47, (unsigned int)v64, v60[0]);
        v57 = v52;
        if ( v52 < 0 )
          break;
        v9 -= (unsigned int)v65;
        v48 += 24;
        v50 = v66 + 256;
        v66 += 256;
        v47 += v53;
        if ( ++v49 >= v40 )
        {
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
          goto LABEL_70;
        }
      }
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
        "CAuthInfo::WriteToCache",
        0xFB8u,
        v52,
        "hr = StringCchCopyW(pKeyword, cbKeyword, (LPCWSTR)wstrSampleKeyword)");
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v60);
    }
    else
    {
LABEL_70:
      if ( !(unsigned int)CredmanUtility::CredWriteW(&Credential, v37) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v57 = LastError;
        if ( LastError < 0 )
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
            "CAuthInfo::WriteToCache",
            0xFC0u,
            LastError,
            "hr = HRESULT_FROM_WIN32(GetLastError())");
      }
    }
    operator delete(v39);
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&v69);
    v43 = v38;
    goto LABEL_50;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
    "CAuthInfo::WriteToCache",
    0xF50u,
    v35,
    "hr = EncryptCredentialsInSystemContext(&executionContext, strTokenBlob.GetBuffer(), strTokenBlob.GetLength() * sizeo"
    "f(char), credsOut)");
  CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)v60);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v80);
LABEL_80:
  v55 = v57;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v79);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v77);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v67);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v68);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  return v55;
}

```

## disassembly

```asm
0x180068ba0  mov     [rsp-8+arg_10], rbx
0x180068ba5  push    rbp
0x180068ba6  push    rsi
0x180068ba7  push    rdi
0x180068ba8  push    r12
0x180068baa  push    r13
0x180068bac  push    r14
0x180068bae  push    r15
0x180068bb0  lea     rbp, [rsp-200h]
0x180068bb8  sub     rsp, 300h
0x180068bbf  mov     rax, cs:__security_cookie
0x180068bc6  xor     rax, rsp
0x180068bc9  mov     [rbp+230h+var_40], rax
0x180068bd0  mov     [rsp+330h+var_2DB], r9b
0x180068bd5  mov     r15b, r8b
0x180068bd8  mov     [rsp+330h+var_2DC], r8b
0x180068bdd  mov     rbx, rdx
0x180068be0  mov     rdi, rcx
0x180068be3  mov     [rbp+230h+var_2A8], rcx
0x180068be7  mov     rax, [rbp+230h+arg_20]
0x180068bee  mov     [rbp+230h+var_2B0], rax
0x180068bf2  mov     r14, [rbp+230h+arg_28]
0x180068bf9  xor     r13d, r13d
0x180068bfc  mov     [rsp+330h+var_2E0], r13d
0x180068c01  lea     rcx, [rbp+230h+var_248]
0x180068c05  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068c0a  nop
0x180068c0b  lea     rcx, [rbp+230h+var_290]
0x180068c0f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068c14  nop
0x180068c15  lea     rcx, [rbp+230h+var_298]
0x180068c19  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068c1e  nop
0x180068c1f  mov     [rbp+230h+var_240], r13
0x180068c23  mov     [rbp+230h+var_230], r13
0x180068c27  mov     [rbp+230h+var_238], r13
0x180068c2b  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180068c30  test    al, al
0x180068c32  jz      short loc_180068C41
0x180068c34  mov     cl, 1; this
0x180068c36  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180068c3b  test    al, al
0x180068c3d  mov     al, cl
0x180068c3f  jnz     short loc_180068C44
0x180068c41  mov     al, r13b
0x180068c44  lea     rcx, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180068c4b  mov     qword ptr [rbp+230h+var_268], rcx
0x180068c4f  mov     qword ptr [rbp+230h+var_268+8], r14
0x180068c53  mov     [rbp+230h+var_258], r13
0x180068c57  mov     [rbp+230h+var_250], al
0x180068c5a  lea     rcx, [rbp+230h+var_268]; this
0x180068c5e  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180068c63  mov     rsi, rax
0x180068c66  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180068c6b  test    al, al
0x180068c6d  jz      short loc_180068C7A
0x180068c6f  mov     cl, 1; this
0x180068c71  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180068c76  test    al, al
0x180068c78  jnz     short loc_180068C7D
0x180068c7a  mov     cl, r13b
0x180068c7d  mov     [rbp+230h+var_280], rdi
0x180068c81  mov     [rbp+230h+var_278], r13
0x180068c85  mov     [rbp+230h+var_270], cl
0x180068c88  lea     rax, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180068c8f  mov     [rbp+230h+var_288], rax
0x180068c93  lea     rcx, [rbp+230h+var_288]; this
0x180068c97  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180068c9c  mov     [rsp+330h+var_2F0], rsi
0x180068ca1  mov     [rsp+330h+var_2F8], rbx
0x180068ca6  mov     [rsp+330h+var_300], rax
0x180068cab  lea     rax, aWszusernameLsW_0; "wszUserName=%ls, wszVirtualAppName=%ls,"...
0x180068cb2  mov     [rsp+330h+var_308], rax
0x180068cb7  lea     r12, aCauthinfoWrite; "CAuthInfo::WriteToCache"
0x180068cbe  mov     [rsp+330h+var_310], r12
0x180068cc3  lea     r9, [rsp+330h+var_2E0]
0x180068cc8  mov     r8d, 0F27h
0x180068cce  lea     rsi, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180068cd5  mov     rdx, rsi
0x180068cd8  lea     rcx, [rbp+230h+var_1D0]
0x180068cdc  call    ??0?$CTraceFuncW@J@@QEAA@PEBDKAEAJ0PEBGZZ; CTraceFuncW<long>::CTraceFuncW<long>(char const *,ulong,long &,char const *,ushort const *,...)
0x180068ce1  nop
0x180068ce2  lea     rcx, [rbp+230h+var_288]; this
0x180068ce6  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180068ceb  nop
0x180068cec  lea     rcx, [rbp+230h+var_268]; this
0x180068cf0  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180068cf5  test    rdi, rdi
0x180068cf8  jz      loc_180069390
0x180068cfe  cmp     [rdi], r13w
0x180068d02  jz      loc_180069390
0x180068d08  test    r15b, r15b
0x180068d0b  jz      loc_180068D9B
0x180068d11  test    rbx, rbx
0x180068d14  jz      loc_180069390
0x180068d1a  cmp     [rbx], r13w
0x180068d1e  jz      loc_180069390
0x180068d24  or      r15, 0FFFFFFFFFFFFFFFFh
0x180068d28  mov     rax, r15
0x180068d2b  inc     rax
0x180068d2e  cmp     [rbx+rax*2], r13w
0x180068d33  jnz     short loc_180068D2B
0x180068d35  cmp     rax, 100h
0x180068d3b  jbe     short loc_180068D4F
0x180068d3d  lea     rax, aVirtappnamecha; "virtAppNameCharLen <= PPCRL_MAX_VIRTUAL"...
0x180068d44  mov     r8d, 0F34h
0x180068d4a  jmp     loc_18006939D
0x180068d4f  lea     rdx, [rbp+230h+var_290]
0x180068d53  mov     rcx, rbx
0x180068d56  call    ?GetVirtualAppTargetName@CAuthInfo@@SAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAuthInfo::GetVirtualAppTargetName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180068d5b  mov     rdx, rbx
0x180068d5e  lea     rcx, [rbp+230h+var_298]
0x180068d62  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180068d67  lea     rdx, aDidsystem; "DIDSystem"
0x180068d6e  mov     rcx, [rbp+230h+var_298]
0x180068d72  call    cs:__imp__o__wcsicmp
0x180068d78  test    eax, eax
0x180068d7a  jz      short loc_180068D96
0x180068d7c  lea     rdx, aDidlogical; "DIDLogical"
0x180068d83  mov     rcx, [rbp+230h+var_298]
0x180068d87  call    cs:__imp__o__wcsicmp
0x180068d8d  test    eax, eax
0x180068d8f  jz      short loc_180068D96
0x180068d91  mov     r12b, r13b
0x180068d94  jmp     short loc_180068DD5
0x180068d96  mov     r12b, 1
0x180068d99  jmp     short loc_180068DD5
0x180068d9b  or      r15, 0FFFFFFFFFFFFFFFFh
0x180068d9f  mov     rax, r15
0x180068da2  inc     rax
0x180068da5  cmp     [rdi+rax*2], r13w
0x180068daa  jnz     short loc_180068DA2
0x180068dac  cmp     rax, 100h
0x180068db2  jbe     short loc_180068DC6
0x180068db4  lea     rax, aUsernamecharle; "userNameCharLen <= PPCRL_MAX_IDLEN"
0x180068dbb  mov     r8d, 0F41h
0x180068dc1  jmp     loc_18006939D
0x180068dc6  mov     r12b, r13b
0x180068dc9  lea     rdx, [rbp+230h+var_290]
0x180068dcd  mov     rcx, rdi; Src
0x180068dd0  call    ?GetUserTargetName@CAuthInfo@@SAXPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CAuthInfo::GetUserTargetName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180068dd5  xor     edi, edi
0x180068dd7  mov     [rbp+230h+var_2A0], rdi
0x180068ddb  call    ?PPTraceShouldRedact@@YA_NXZ; PPTraceShouldRedact(void)
0x180068de0  test    al, al
0x180068de2  jz      short loc_180068DF1
0x180068de4  mov     cl, 1; this
0x180068de6  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x180068deb  test    al, al
0x180068ded  mov     al, cl
0x180068def  jnz     short loc_180068DF4
0x180068df1  mov     al, dil
0x180068df4  lea     rcx, ??_7PPRedactedStringW@@6B@; const PPRedactedStringW::`vftable'
0x180068dfb  mov     [rsp+330h+var_2D8], rcx
0x180068e00  mov     rsi, [rbp+230h+var_290]
0x180068e04  mov     [rsp+330h+var_2D8+8], rsi
0x180068e09  mov     [rsp+330h+var_2C8], rdi
0x180068e0e  mov     [rsp+330h+var_2C0], al
0x180068e12  lea     rcx, [rsp+330h+var_2D8]; this
0x180068e17  call    ?GetString@PPRedactedStringW@@QEAAPEBGXZ; PPRedactedStringW::GetString(void)
0x180068e1c  mov     [rsp+330h+var_310], rax
0x180068e21  lea     r9, aWstrtargetname_1; "wstrTargetName=%ls"
0x180068e28  mov     r8d, 0F46h; unsigned int
0x180068e2e  lea     rdx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180068e35  mov     ecx, 5; unsigned __int8
0x180068e3a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180068e3f  nop
0x180068e40  lea     rcx, [rsp+330h+var_2D8]; this
0x180068e45  call    ??1PPRedactedStringW@@QEAA@XZ; PPRedactedStringW::~PPRedactedStringW(void)
0x180068e4a  test    r14, r14
0x180068e4d  jz      loc_180068FB8
0x180068e53  cmp     [r14], di
0x180068e57  jz      loc_180068FB8
0x180068e5d  lea     rcx, [rbp+230h+var_1B0]; this
0x180068e64  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x180068e69  nop
0x180068e6a  xorps   xmm0, xmm0
0x180068e6d  movups  [rbp+230h+var_268], xmm0
0x180068e71  lea     rcx, [rsp+330h+var_2D8]
0x180068e76  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068e7b  nop
0x180068e7c  lea     rax, [rbp+230h+var_C8]
0x180068e83  mov     [rbp+230h+Block], rax
0x180068e8a  mov     r8d, 0FDE9h
0x180068e90  mov     rdx, r14
0x180068e93  lea     rcx, [rbp+230h+Block]
0x180068e9a  call    ?Init@?$CW2AEX@$0IA@@ATL@@AEAAXPEBGI@Z; ATL::CW2AEX<128>::Init(ushort const *,uint)
0x180068e9f  nop
0x180068ea0  mov     rdx, [rbp+230h+Block]
0x180068ea7  lea     rcx, [rsp+330h+var_2B8]
0x180068eac  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(char const *)
0x180068eb1  nop
0x180068eb2  mov     rdx, rax
0x180068eb5  lea     rcx, [rsp+330h+var_2D8]
0x180068eba  call    ??4?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAAAEAV0@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x180068ebf  nop
0x180068ec0  lea     rcx, [rsp+330h+var_2B8]
0x180068ec5  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068eca  nop
0x180068ecb  mov     rcx, [rbp+230h+Block]; Block
0x180068ed2  lea     rax, [rbp+230h+var_C8]
0x180068ed9  cmp     rcx, rax
0x180068edc  jz      short loc_180068EE3
0x180068ede  call    free
0x180068ee3  mov     rax, [rsp+330h+var_2D8]
0x180068ee8  movsxd  rbx, dword ptr [rax-10h]
0x180068eec  lea     rcx, [rsp+330h+var_2D8]
0x180068ef1  call    ?GetBuffer@?$CSimpleStringT@D$0A@@ATL@@QEAAPEADXZ; ATL::CSimpleStringT<char,0>::GetBuffer(void)
0x180068ef6  lea     r9, [rbp+230h+var_268]
0x180068efa  mov     r8, rbx
0x180068efd  mov     rdx, rax
0x180068f00  lea     rcx, [rbp+230h+var_1B0]
0x180068f07  call    ??$EncryptCredentialsInSystemContext@PEAD@CAuthInfo@@SAJPEAVIServiceExecutionContext@@PEAD_KAEAU_CRYPTOAPI_BLOB@@@Z; CAuthInfo::EncryptCredentialsInSystemContext<char *>(IServiceExecutionContext *,char *,unsigned __int64,_CRYPTOAPI_BLOB &)
0x180068f0c  mov     [rsp+330h+var_2E0], eax
0x180068f10  test    eax, eax
0x180068f12  jns     short loc_180068F59
0x180068f14  lea     rcx, aHrEncryptcrede_0; "hr = EncryptCredentialsInSystemContext("...
0x180068f1b  mov     [rsp+330h+var_310], rcx; char *
0x180068f20  mov     r9d, eax; int
0x180068f23  mov     r8d, 0F50h; unsigned int
0x180068f29  lea     rdx, aCauthinfoWrite; "CAuthInfo::WriteToCache"
0x180068f30  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180068f37  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180068f3c  nop
0x180068f3d  lea     rcx, [rsp+330h+var_2D8]
0x180068f42  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068f47  nop
0x180068f48  lea     rcx, [rbp+230h+var_1B0]; this
0x180068f4f  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x180068f54  jmp     loc_1800693B8
0x180068f59  lea     rcx, [rbp+230h+var_240]
0x180068f5d  call    ?Clear@?$Auto@PEADV?$LocalAllocFunctor@PEAD@@VDummyContext@@@@QEAAXXZ; Auto<char *,LocalAllocFunctor<char *>,DummyContext>::Clear(void)
0x180068f62  mov     rax, qword ptr [rbp+230h+var_268+8]
0x180068f66  mov     [rbp+230h+var_2A0], rax
0x180068f6a  mov     [rbp+230h+var_240], rax
0x180068f6e  mov     r13d, dword ptr [rbp+230h+var_268]
0x180068f72  lea     rcx, [rsp+330h+var_2D8]
0x180068f77  call    ??1?$CAutoZeroMemoryStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@@QEAA@XZ; CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180068f7c  nop
0x180068f7d  lea     rcx, [rbp+230h+var_1B0]; this
0x180068f84  call    ??1ServiceExecutionContext@@UEAA@XZ; ServiceExecutionContext::~ServiceExecutionContext(void)
0x180068f89  cmp     r13d, 4000h
0x180068f90  jbe     short loc_180068FB8
0x180068f92  mov     r9d, 80048886h
0x180068f98  lea     rax, aCbtokenlenCred; "cbTokenLen <= CRED_MAX_ATTRIBUTES * CRE"...
0x180068f9f  mov     r8d, 0F58h
0x180068fa5  lea     rdx, aCauthinfoWrite; "CAuthInfo::WriteToCache"
0x180068fac  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180068fb3  jmp     loc_1800693A9
0x180068fb8  xor     edx, edx; Val
0x180068fba  lea     r8d, [rdx+50h]; Size
0x180068fbe  lea     rcx, [rbp+230h+Credential]; void *
0x180068fc2  call    memset_0
0x180068fc7  xor     ecx, ecx
0x180068fc9  mov     ebx, ecx
0x180068fcb  mov     qword ptr [rbp+230h+var_268], rcx
0x180068fcf  mov     [rbp+230h+var_288], rcx
0x180068fd3  mov     [rbp+230h+var_278], rcx
0x180068fd7  mov     [rbp+230h+var_280], rcx
0x180068fdb  mov     edi, ecx
0x180068fdd  mov     [rsp+330h+var_2B8], rcx
0x180068fe2  mov     r14d, ecx
0x180068fe5  test    r13d, r13d
0x180068fe8  jz      short loc_180068FF5
0x180068fea  lea     r14d, [r13+0FFh]
0x180068ff1  shr     r14d, 8
0x180068ff5  mov     eax, 1
0x180068ffa  mov     [rbp+230h+Credential.Type], eax
0x180068ffd  mov     [rbp+230h+Credential.TargetName], rsi
0x180069001  cmp     [rsp+330h+var_2DC], cl
0x180069005  jz      short loc_180069019
0x180069007  test    r12b, r12b
0x18006900a  jnz     short loc_180069019
0x18006900c  mov     [rbp+230h+Credential.Persist], eax
0x18006900f  mov     rax, [rbp+230h+var_2A8]
0x180069013  mov     [rbp+230h+Credential.UserName], rax
0x180069017  jmp     short loc_180069044
0x180069019  mov     [rbp+230h+Credential.Persist], 2
0x180069020  mov     rax, [rbp+230h+var_2A8]
0x180069024  mov     [rbp+230h+Credential.UserName], rax
0x180069028  test    r12b, r12b
0x18006902b  jz      short loc_180069044
0x18006902d  call    IsMsaDevice_FreeDeviceAuthXTokenPresent
0x180069032  xor     ecx, ecx
0x180069034  test    al, al
0x180069036  jz      short loc_180069044
0x180069038  lea     rcx, [rbp+230h+Credential.Persist]
0x18006903c  call    cs:__imp_MsaDevice_OverrideTokenPersistence
0x180069042  xor     ecx, ecx
0x180069044  mov     rsi, [rbp+230h+var_2B0]
0x180069048  test    rsi, rsi
0x18006904b  jz      loc_18006911F
0x180069051  cmp     [rsi], cx
0x180069054  jz      loc_18006911F
0x18006905a  lea     rcx, [rbp+230h+var_1B0]; this
0x180069061  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x180069066  nop
0x180069067  xorps   xmm0, xmm0
0x18006906a  movups  xmmword ptr [rsp+330h+var_2D8], xmm0
0x18006906f  xor     r12d, r12d
  ... truncated ...
```
