# IdentityStorage::ReadCredentialInformation(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_ModernIdentityType,ulong &,CIdentityTokenCacheArray &,ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>> &,bool,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x180014004`
- end: `0x180014abd`
- name: `?ReadCredentialInformation@IdentityStorage@@AEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4_ModernIdentityType@@AEAKAEAVCIdentityTokenCacheArray@@AEAV?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@3@_N5V23@@Z`
- size: `2745`
- prototype: `__int64 __usercall@<rax>(IdentityStorage *this@<rcx>, __int64, __int64, char, char, void *)`
- caller_count: `3`
- callee_count: `43`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180014ac4`
- `0x18003d510`
- `0x18003f0f8`

## callees

- `0x180002eb4`
- `0x1800034c0`
- `0x1800035cc`
- `0x180003990`
- `0x180003c44`
- `0x180003cf0`
- `0x180004824`
- `0x180004910`
- `0x180004b00`
- `0x180004e30`
- `0x180004fdc`
- `0x1800050f8`
- `0x18000535c`
- `0x1800061a8`
- `0x180006aa4`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010b58`
- `0x180010b80`
- `0x1800113e8`
- `0x180011c1c`
- `0x180012288`
- `0x18001261c`
- `0x1800128b8`
- `0x180013434`
- `0x180014004`
- `0x180016010`
- `0x18001606c`
- `0x1800163ac`
- `0x180017994`
- `0x18003b6e4`
- `0x18003c388`
- `0x18003c5f4`
- `0x18003c650`
- `0x18003d848`
- `0x18003d980`
- `0x18003dae0`
- `0x18003e584`
- `0x18003e824`
- `0x18003e8e0`
- `0x180050d58`
- `0x180058010`

## import_xrefs

- `ntdll!WinSqmAddToStreamEx` at `0x1800148ff`
- `ntdll!WinSqmAddToStreamEx` at `0x1800148ff`
- `ntdll!wcsstr` at `0x180014509`
- `ntdll!wcsstr` at `0x180014509`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180014721`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180014721`

## string_xrefs

- `0x18001408c`: `IdentityStorage::ReadCredentialInformation`
- `0x1800141d4`: `IdentityStorage::ReadCredentialInformation`
- `0x180014546`: `IdentityStorage::ReadCredentialInformation`
- `0x1800149a7`: `IdentityStorage::ReadCredentialInformation`
- `0x1800149e6`: `IdentityStorage::ReadCredentialInformation`
- `0x1800141bf`: `hr = registryHelper.ReadDwordFromRegistry(nullptr, registryKey, ApplicationFlags, &applicationFlag)`
- `0x180014262`: `hr = registryHelper.ReadBufferFromRegistry(nullptr, registryKey, GetIdentityKey(identityType), RRF_RT_REG_SZ, &apDefaultIdBuffer, &defaultIdBufferSize)`
- `0x180014355`: `hr = registryHelper.GetRootKey(pRegistryFunctions, HKEY_CURRENT_USER, &useCurrentUserKey, &hkeyCurrentUser)`
- `0x180014705`: `tokenArray.SetCount(tokenBag.GetObject().tokenCount)`
- `0x180014880`: `ReadCredentialInformation for registryKey=%s failed with hr=%x continuing.`
- `0x180014115`: `Software\Microsoft\IdentityCRL\Immersive\%s\Token\`
- `0x1800142f5`: `Software\Microsoft\IdentityCRL\Immersive\%s\Token\`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall IdentityStorage::ReadCredentialInformation(
        struct IExecutionContextLite **this,
        const wchar_t **a2,
        unsigned int a3,
        _DWORD *a4,
        __int64 a5,
        __int64 a6,
        char a7,
        char a8,
        void *a9)
{
  _DWORD *v9; // r12
  __int64 v13; // rcx
  unsigned int *v14; // rax
  __int64 v15; // r13
  __int64 EnvironmentSpecificRegistryKey; // rax
  __int64 v17; // rdx
  unsigned __int16 *v18; // rbx
  int *v19; // rdi
  __int64 v20; // rbx
  int ValueFrom; // eax
  __int64 v22; // rcx
  const unsigned __int16 *IdentityKey; // rax
  int v24; // eax
  __int64 v25; // rcx
  __int64 IdentityTokenKey; // rax
  struct IRegistryFunctions *v27; // rsi
  __int64 v28; // rax
  RegistryHelper *v29; // rcx
  int RootKey; // eax
  signed int v31; // eax
  signed int v32; // eax
  unsigned int v33; // r14d
  __int64 (__fastcall *v34)(struct IRegistryFunctions *, _QWORD, _QWORD, __int64, unsigned int *, _QWORD, _QWORD, _QWORD, _QWORD); // rdi
  __int64 BufferSetLength; // rax
  signed int v36; // edi
  const wchar_t *v37; // rdi
  const wchar_t **Lower; // rax
  int *v39; // rsi
  __int64 v40; // rdi
  __int64 v41; // rdx
  int *v42; // rsi
  __int64 v43; // rdi
  __int64 v44; // rcx
  int v45; // ebx
  __int64 TokenInvalidationTime; // r12
  __int64 TimeSkew; // rcx
  __time64_t v48; // rdx
  unsigned int i; // r14d
  __int64 v50; // rbx
  __int64 v51; // rbx
  __int64 v52; // rbx
  __int64 v53; // rax
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rcx
  const wchar_t **v59; // rbx
  int IdentityProperties; // eax
  __int64 Buffer; // rax
  const wchar_t *v62; // rax
  int PairwiseId; // eax
  unsigned int v64; // ebx
  HKEY *v66; // [rsp+20h] [rbp-E0h]
  int v67; // [rsp+20h] [rbp-E0h]
  unsigned __int8 **v68; // [rsp+28h] [rbp-D8h]
  int v69; // [rsp+70h] [rbp-90h] BYREF
  __time64_t Time; // [rsp+78h] [rbp-88h] BYREF
  __int64 v71; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v72; // [rsp+88h] [rbp-78h] BYREF
  __int64 v73; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v74; // [rsp+98h] [rbp-68h] BYREF
  __int64 v75; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v76; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v77; // [rsp+B0h] [rbp-50h] BYREF
  __m256i v78; // [rsp+B8h] [rbp-48h] BYREF
  struct IExecutionContextLite **v79; // [rsp+D8h] [rbp-28h] BYREF
  unsigned int v80; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v81; // [rsp+E8h] [rbp-18h]
  HKEY v82; // [rsp+F0h] [rbp-10h] BYREF
  struct IExecutionContextLite *v83; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int8 *v84; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v85[8]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v86[8]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v87[3]; // [rsp+118h] [rbp+18h] BYREF
  struct IExecutionContextLite *v88; // [rsp+130h] [rbp+30h] BYREF
  int *v89[4]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v90[11]; // [rsp+158h] [rbp+58h] BYREF
  unsigned int v91; // [rsp+1C0h] [rbp+C0h] BYREF
  const wchar_t **v92; // [rsp+1C8h] [rbp+C8h]
  _DWORD *v93; // [rsp+1D8h] [rbp+D8h]

  v93 = a4;
  v92 = a2;
  v9 = a4;
  v69 = 0;
  v88 = *this;
  v84 = 0;
  v91 = 0;
  v83 = v88;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v76);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v73);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v75);
  v79 = &v88;
  v13 = 16;
  v14 = &v80;
  do
  {
    *(_BYTE *)v14 = 0;
    v14 = (unsigned int *)((char *)v14 + 1);
    --v13;
  }
  while ( v13 );
  v77 = 0;
  v90[0] = "IdentityStorage::ReadCredentialInformation";
  v90[1] = &v69;
  v90[2] = 1;
  v90[3] = &dword_18006F75C;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::ReadCredentialInformation",
    (const char *)0x376,
    0,
    (const unsigned __int16 *)v66);
  ErrorVerifier::ErrorVerifier(
    (ErrorVerifier *)v89,
    "IdentityStorage::ReadCredentialInformation",
    &v69,
    0xBu,
    &qword_18006F730);
  v15 = a5;
  ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::SetCount(a5, 0);
  ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::SetCount(a6, 0);
  *v9 = 0;
  EnvironmentSpecificRegistryKey = IdentityStorage::GetEnvironmentSpecificRegistryKey(
                                     this,
                                     &v71,
                                     L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Token\\");
  v17 = *(_QWORD *)ATL::operator+(&Time, EnvironmentSpecificRegistryKey, a2);
  v18 = v76;
  v19 = (int *)(v76 - 12);
  if ( (unsigned __int16 *)(v17 - 24) != v76 - 12 )
  {
    if ( v19[4] >= 0 && *(_QWORD *)(v17 - 24) == *(_QWORD *)v19 )
    {
      v20 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
      ATL::CStringData::Release((ATL::CStringData *)v19);
      v18 = (unsigned __int16 *)(v20 + 24);
      v76 = v18;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v76, v17, *(unsigned int *)(v17 - 16));
      v18 = v76;
    }
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Time);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  ValueFrom = RegistryHelper::ReadValueFromRegistry<unsigned long>(
                (unsigned int)&v83,
                0,
                (_DWORD)v18,
                (unsigned int)L"ApplicationFlags",
                v67,
                (__int64)v9);
  v69 = ValueFrom;
  if ( ValueFrom < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::ReadCredentialInformation",
      0x385u,
      ValueFrom,
      "hr = registryHelper.ReadDwordFromRegistry(nullptr, registryKey, ApplicationFlags, &applicationFlag)");
    goto LABEL_80;
  }
  if ( (*v9 & 0xFFFFFFF8) != 0 )
  {
    v69 = -2147024894;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::ReadCredentialInformation",
      0x388u,
      -2147024894,
      "(applicationFlag & ~ModernApplication::All) == 0");
    goto LABEL_80;
  }
  if ( !a8 )
  {
    IdentityKey = (const unsigned __int16 *)IdentityStorage::GetIdentityKey(v22, a3);
    v24 = RegistryHelper::ReadBufferFromRegistry((RegistryHelper *)&v83, 0, v18, IdentityKey, 2u, &v84, &v91);
    v69 = v24;
    if ( v24 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        "IdentityStorage::ReadCredentialInformation",
        0x38Du,
        v24,
        "hr = registryHelper.ReadBufferFromRegistry(nullptr, registryKey, GetIdentityKey(identityType), RRF_RT_REG_SZ, &a"
        "pDefaultIdBuffer, &defaultIdBufferSize)");
      goto LABEL_80;
    }
    if ( !v91 )
    {
      v69 = -2147024894;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        "IdentityStorage::ReadCredentialInformation",
        0x38Fu,
        -2147024894,
        "defaultIdBufferSize != 0");
      goto LABEL_80;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v73, v84);
    IdentityTokenKey = IdentityStorage::GetIdentityTokenKey(v25, a3);
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v75, IdentityTokenKey);
LABEL_52:
    if ( a7 == 1 )
    {
      if ( CWLIDCCHelper::HasClockChanged(*this, &v77) )
      {
        memset((char *)v78.m256i_i64 + 4, 0, 28);
        v59 = v92;
        v62 = *v92;
        v78.m256i_i32[0] = 16;
        if ( !v62 || !*v62 )
          v62 = L"(null)";
        v78.m256i_i64[1] = (__int64)v62;
        v78.m256i_i32[1] = 2;
        v78.m256i_i64[2] = 0x100000010LL;
        v78.m256i_i32[6] = v77;
        WinSqmAddToStreamEx(0, 11246, 2, &v78, 0);
        TracePrintW(
          4u,
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          0x41Bu,
          L"HasClockChanged returned true.");
        v69 = -2147024894;
        goto LABEL_63;
      }
      v45 = IdentityStorage::ReadCredentialInformation<ModernAppTokenBagSerializer,AutoSerializedObject<ModernAppTokenBagSerializer,_ModernAppTokenBag>>(
              v44,
              v18,
              v75,
              &v88,
              &v83,
              &v79);
      v69 = v45;
      if ( v45 < 0 )
      {
        Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v76);
        LODWORD(v68) = v45;
        TracePrintW(
          3u,
          "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
          0x404u,
          L"ReadCredentialInformation for registryKey=%s failed with hr=%x continuing.",
          Buffer,
          v68);
      }
      else
      {
        Time = 0;
        TokenInvalidationTime = IdentityStorage::GetTokenInvalidationTime((IdentityStorage *)this);
        if ( !(unsigned __int8)ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::SetCount(v15, v80) )
        {
          v69 = -2147024882;
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
            "IdentityStorage::ReadCredentialInformation",
            0x3EBu,
            -2147024882,
            "tokenArray.SetCount(tokenBag.GetObject().tokenCount)");
          goto LABEL_80;
        }
        _time64(&Time);
        TimeSkew = (int)IdentityStorage::GetTimeSkew((IdentityStorage *)this);
        v48 = Time - TimeSkew;
        Time = v48;
        *(_QWORD *)(v15 + 32) = v48;
        if ( v80 )
        {
          for ( i = 0; i < v80; ++i )
          {
            v50 = *(_QWORD *)(v81 + 48LL * i);
            *(_QWORD *)ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v15, i) = v50;
            v51 = *(_QWORD *)(v81 + 48LL * i + 8);
            *(_QWORD *)(ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v15, i) + 8) = v51;
            LODWORD(v51) = *(_DWORD *)(v81 + 48LL * i + 16);
            *(_DWORD *)(ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v15, i) + 16) = v51;
            v52 = *(_QWORD *)(v81 + 48LL * i + 24);
            v53 = ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v15, i);
            ATL::CSimpleStringT<unsigned short,0>::SetString(v53 + 24, v52);
            v54 = *(_QWORD *)(v81 + 48LL * i + 32);
            v55 = ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v15, i);
            ATL::CSimpleStringT<unsigned short,0>::SetString(v55 + 32, v54);
            v56 = *(_QWORD *)(v81 + 48LL * i + 40);
            v57 = ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::operator[](v15, i);
            ATL::CSimpleStringT<unsigned short,0>::SetString(v57 + 40, v56);
          }
          v48 = Time;
        }
        IdentityStorage::RemoveExpiredTokens(TimeSkew, v48, v15);
        IdentityStorage::RemoveInvalidatedTokens(v58, TokenInvalidationTime, v15);
        v9 = v93;
      }
    }
    v59 = v92;
LABEL_63:
    IdentityProperties = IdentityStorage::GetIdentityProperties(this, v73, a6);
    v69 = IdentityProperties;
    if ( IdentityProperties >= 0 )
    {
      if ( (*(_BYTE *)v9 & 1) == 0 )
      {
        IdentityProperty::IdentityProperty((IdentityProperty *)v85);
        ATL::CSimpleStringT<unsigned short,0>::SetString(v85, L"PWID");
        PairwiseId = IdentityStorage::GetPairwiseId(this, v73, *v59, v86);
        v69 = PairwiseId;
        if ( PairwiseId < 0 )
        {
          if ( PairwiseId == -2147024894 )
          {
            PairwiseId = 0;
            v69 = 0;
          }
        }
        else
        {
          ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::Add(a6, v85);
          PairwiseId = v69;
        }
        if ( PairwiseId < 0 )
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
            "IdentityStorage::ReadCredentialInformation",
            0x437u,
            PairwiseId,
            "hr");
        OnlineIdServiceTicketRequestInternal::~OnlineIdServiceTicketRequestInternal((OnlineIdServiceTicketRequestInternal *)v85);
      }
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
        "IdentityStorage::ReadCredentialInformation",
        0x421u,
        IdentityProperties,
        "hr = GetIdentityProperties(defaultId, identityPropertyArray)");
    }
    goto LABEL_80;
  }
  v27 = (struct IRegistryFunctions *)(*(__int64 (__fastcall **)(struct IExecutionContextLite *))(*(_QWORD *)*this + 8LL))(*this);
  *(_OWORD *)v78.m256i_i8 = 0u;
  v78.m256i_i64[2] = (__int64)v27;
  v87[0] = 0;
  v87[2] = v27;
  v87[1] = 0;
  v28 = IdentityStorage::GetEnvironmentSpecificRegistryKey(
          this,
          &v71,
          L"Software\\Microsoft\\IdentityCRL\\Immersive\\%s\\Token\\");
  ATL::operator+(&Time, v28, a2);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  v74 = 0;
  v72 = 0;
  v82 = HKEY_CURRENT_USER;
  RootKey = RegistryHelper::GetRootKey(v29, v27, &v82, (bool *)&v91, (HKEY *)&v78);
  v69 = RootKey;
  if ( RootKey < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::ReadCredentialInformation",
      0x3A1u,
      RootKey,
      "hr = registryHelper.GetRootKey(pRegistryFunctions, HKEY_CURRENT_USER, &useCurrentUserKey, &hkeyCurrentUser)");
    goto LABEL_79;
  }
  v31 = (*(__int64 (__fastcall **)(struct IRegistryFunctions *, __int64, __time64_t, _QWORD, int, _QWORD *))(*(_QWORD *)v27 + 80LL))(
          v27,
          v78.m256i_i64[0],
          Time,
          0,
          131097,
          v87);
  if ( v31 )
  {
    if ( v31 > 0 )
      v31 = (unsigned __int16)v31 | 0x80070000;
    v69 = v31;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::ReadCredentialInformation",
      0x3A8u,
      v31,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_79;
  }
  v32 = (*(__int64 (__fastcall **)(struct IRegistryFunctions *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *, unsigned int *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v27 + 96LL))(
          v27,
          v87[0],
          0,
          0,
          0,
          0,
          0,
          0,
          &v74,
          &v72,
          0,
          0,
          0);
  if ( v32 )
  {
    if ( v32 > 0 )
      v32 = (unsigned __int16)v32 | 0x80070000;
    v69 = v32;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::ReadCredentialInformation",
      0x3B6u,
      v32,
      "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
    goto LABEL_79;
  }
  ++v72;
  v33 = 0;
  if ( !v74 )
  {
LABEL_49:
    if ( *(_DWORD *)(v73 - 16) && *(_DWORD *)(v75 - 16) )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Time);
      Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v87);
      Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(&v78);
      goto LABEL_52;
    }
    v69 = -2147024894;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
      "IdentityStorage::ReadCredentialInformation",
      0x3DDu,
      -2147024894,
      "!defaultId.IsEmpty() && !regKeyForTicket.IsEmpty()");
LABEL_79:
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Time);
    Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v87);
    Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(&v78);
    goto LABEL_80;
  }
  while ( 1 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v71);
    v91 = v72;
    v34 = *(__int64 (__fastcall **)(struct IRegistryFunctions *, _QWORD, _QWORD, __int64, unsigned int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v27 + 136LL);
    BufferSetLength = ATL::CSimpleStringT<unsigned short,0>::GetBufferSetLength(&v71);
    v36 = v34(v27, v87[0], v33, BufferSetLength, &v91, 0, 0, 0, 0);
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v71, v91);
    if ( v36 == 259 )
      goto LABEL_48;
    if ( v36 )
      break;
    v37 = *(const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(a9);
    Lower = (const wchar_t **)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v71);
    if ( wcsstr(*Lower, v37) )
    {
      LODWORD(v82) = 0;
      v39 = (int *)(v75 - 24);
      if ( v71 - 24 != v75 - 24 )
      {
        if ( v39[4] >= 0 && *(_QWORD *)(v71 - 24) == *(_QWORD *)v39 )
        {
          v40 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v39);
          v75 = v40 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v75, v71, *(unsigned int *)(v71 - 16));
        }
      }
      v41 = *(_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Tokenize(
                         &v71,
                         v85,
                         L"|",
                         &v82);
      v42 = (int *)(v73 - 24);
      if ( v41 - 24 != v73 - 24 )
      {
        if ( v42[4] >= 0 && *(_QWORD *)(v41 - 24) == *(_QWORD *)v42 )
        {
          v43 = ATL::CSimpleStringT<unsigned short,0>::CloneData();
          ATL::CStringData::Release((ATL::CStringData *)v42);
          v73 = v43 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v73, v41, *(unsigned int *)(v41 - 16));
        }
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v85);
LABEL_48:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
      goto LABEL_49;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
    if ( ++v33 >= v74 )
      goto LABEL_49;
  }
  if ( v36 > 0 )
    v36 = (unsigned __int16)v36 | 0x80070000;
  v69 = v36;
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\lib\\immersiveidentitystorage\\identitystorage.cpp",
    "IdentityStorage::ReadCredentialInformation",
    0x3D0u,
    v36,
    "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)");
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v71);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Time);
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(v87);
  Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>::~Auto<HKEY__ *,RegistryFunctor,IRegistryFunctions>(&v78);
LABEL_80:
  if ( v69 < 0 )
  {
    ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::SetCount(a6, 0);
    ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::SetCount(v15, 0);
  }
  v64 = v69;
  ErrorVerifier::CheckAgainstList((const char *)v89[3], *v89[2], (unsigned __int64)v89[1], v89[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v90);
  FreeObject<ModernAppTokenBagSerializer,_ModernAppTokenBag>(v79, &v80);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v75);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v73);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v76);
  CMIDLPtr<unsigned short *>::Clear(&v84);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(a9);
  return v64;
}

```

## disassembly

```asm
0x180014004  mov     [rsp-8+arg_10], rbx
0x180014009  mov     [rsp-8+arg_18], r9
0x18001400e  mov     [rsp-8+arg_8], rdx
0x180014013  push    rbp
0x180014014  push    rsi
0x180014015  push    rdi
0x180014016  push    r12
0x180014018  push    r13
0x18001401a  push    r14
0x18001401c  push    r15
0x18001401e  lea     rbp, [rsp-80h]
0x180014023  sub     rsp, 180h
0x18001402a  mov     r12, r9
0x18001402d  mov     esi, r8d
0x180014030  mov     r14, rdx
0x180014033  mov     r15, rcx
0x180014036  xor     ebx, ebx
0x180014038  mov     [rsp+1B0h+var_140], ebx
0x18001403c  mov     rax, [rcx]
0x18001403f  mov     [rbp+0B0h+var_80], rax
0x180014043  mov     [rbp+0B0h+var_B0], rbx
0x180014047  mov     [rbp+0B0h+arg_0], ebx
0x18001404d  mov     [rbp+0B0h+var_B8], rax
0x180014051  lea     rcx, [rbp+0B0h+var_108]; void *
0x180014055  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001405a  nop
0x18001405b  lea     rcx, [rbp+0B0h+var_120]; void *
0x18001405f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180014064  nop
0x180014065  lea     rcx, [rbp+0B0h+var_110]; void *
0x180014069  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001406e  nop
0x18001406f  lea     rax, [rbp+0B0h+var_80]
0x180014073  mov     [rbp+0B0h+var_D8], rax
0x180014077  lea     ecx, [rbx+10h]
0x18001407a  lea     rax, [rbp+0B0h+var_D0]
0x18001407e  mov     [rax], bl
0x180014080  inc     rax
0x180014083  sub     rcx, 1
0x180014087  jnz     short loc_18001407E
0x180014089  mov     [rbp+0B0h+var_100], ebx
0x18001408c  lea     rdi, aIdentitystorag_8; "IdentityStorage::ReadCredentialInformat"...
0x180014093  mov     [rbp+0B0h+var_58], rdi
0x180014097  lea     rax, [rsp+1B0h+var_140]
0x18001409c  mov     [rbp+0B0h+var_50], rax
0x1800140a0  mov     [rbp+0B0h+var_48], 1
0x1800140a8  lea     rax, dword_18006F75C
0x1800140af  mov     [rbp+0B0h+var_40], rax
0x1800140b3  xor     r9d, r9d; unsigned int
0x1800140b6  mov     r8d, 376h; char *
0x1800140bc  mov     rdx, rdi; char *
0x1800140bf  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800140c6  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800140cb  nop
0x1800140cc  lea     rax, qword_18006F730
0x1800140d3  mov     [rsp+1B0h+var_190], rax; int *
0x1800140d8  mov     r9d, 0Bh; unsigned __int64
0x1800140de  lea     r8, [rsp+1B0h+var_140]; int *
0x1800140e3  mov     rdx, rdi; char *
0x1800140e6  lea     rcx, [rbp+0B0h+var_78]; this
0x1800140ea  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800140ef  nop
0x1800140f0  xor     edx, edx
0x1800140f2  mov     r13, [rbp+0B0h+arg_20]
0x1800140f9  mov     rcx, r13
0x1800140fc  call    ?SetCount@?$CAtlArray@UIdentityToken@@V?$CElementTraits@UIdentityToken@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<IdentityToken,ATL::CElementTraits<IdentityToken>>::SetCount(unsigned __int64,int)
0x180014101  nop
0x180014102  xor     edx, edx
0x180014104  mov     rcx, [rbp+0B0h+arg_28]
0x18001410b  call    ?SetCount@?$CAtlArray@UIdentityProperty@@V?$CElementTraits@UIdentityProperty@@@ATL@@@ATL@@QEAA_N_KH@Z; ATL::CAtlArray<IdentityProperty,ATL::CElementTraits<IdentityProperty>>::SetCount(unsigned __int64,int)
0x180014110  nop
0x180014111  mov     [r12], ebx
0x180014115  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x18001411c  lea     rdx, [rbp+0B0h+var_130]
0x180014120  mov     rcx, r15
0x180014123  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x180014128  nop
0x180014129  mov     r8, r14
0x18001412c  mov     rdx, rax
0x18001412f  lea     rcx, [rsp+1B0h+Time]
0x180014134  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014139  nop
0x18001413a  mov     rdx, [rax]
0x18001413d  lea     rcx, [rdx-18h]
0x180014141  mov     rbx, [rbp+0B0h+var_108]
0x180014145  lea     rdi, [rbx-18h]
0x180014149  cmp     rcx, rdi
0x18001414c  jz      short loc_180014187
0x18001414e  cmp     dword ptr [rdi+10h], 0
0x180014152  jl      short loc_180014176
0x180014154  mov     rax, [rdi]
0x180014157  cmp     [rcx], rax
0x18001415a  jnz     short loc_180014176
0x18001415c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180014161  mov     rbx, rax
0x180014164  mov     rcx, rdi; this
0x180014167  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001416c  add     rbx, 18h
0x180014170  mov     [rbp+0B0h+var_108], rbx
0x180014174  jmp     short loc_180014187
0x180014176  mov     r8d, [rdx-10h]
0x18001417a  lea     rcx, [rbp+0B0h+var_108]
0x18001417e  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180014183  mov     rbx, [rbp+0B0h+var_108]
0x180014187  lea     rcx, [rsp+1B0h+Time]; void *
0x18001418c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180014191  nop
0x180014192  lea     rcx, [rbp+0B0h+var_130]; void *
0x180014196  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18001419b  mov     [rsp+1B0h+var_188], r12
0x1800141a0  lea     r9, aApplicationfla_0; "ApplicationFlags"
0x1800141a7  mov     r8, rbx
0x1800141aa  xor     edx, edx
0x1800141ac  lea     rcx, [rbp+0B0h+var_B8]
0x1800141b0  call    ??$ReadValueFromRegistry@K@RegistryHelper@@AEAAJPEAUHKEY__@@PEBG1KPEAK@Z; RegistryHelper::ReadValueFromRegistry<ulong>(HKEY__ *,ushort const *,ushort const *,ulong,ulong *)
0x1800141b5  mov     [rsp+1B0h+var_140], eax
0x1800141b9  xor     edi, edi
0x1800141bb  test    eax, eax
0x1800141bd  jns     short loc_1800141EC
0x1800141bf  lea     r8, aHrRegistryhelp_5; "hr = registryHelper.ReadDwordFromRegist"...
0x1800141c6  mov     [rsp+1B0h+var_190], r8; char *
0x1800141cb  mov     r8d, 385h; unsigned int
0x1800141d1  mov     r9d, eax; int
0x1800141d4  lea     rdx, aIdentitystorag_8; "IdentityStorage::ReadCredentialInformat"...
0x1800141db  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\li"...
0x1800141e2  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800141e7  jmp     loc_180014A18
0x1800141ec  test    dword ptr [r12], 0FFFFFFF8h
0x1800141f4  jz      short loc_180014218
0x1800141f6  mov     r14d, 80070002h
0x1800141fc  mov     [rsp+1B0h+var_140], r14d
0x180014201  lea     rax, aApplicationfla; "(applicationFlag & ~ModernApplication::"...
0x180014208  mov     [rsp+1B0h+var_190], rax
0x18001420d  mov     r9d, r14d
0x180014210  mov     r8d, 388h
0x180014216  jmp     short loc_1800141D4
0x180014218  cmp     [rbp+0B0h+arg_38], dil
0x18001421f  jnz     loc_1800142CB
0x180014225  mov     edx, esi
0x180014227  call    ?GetIdentityKey@IdentityStorage@@AEAAPEBGW4_ModernIdentityType@@@Z; IdentityStorage::GetIdentityKey(_ModernIdentityType)
0x18001422c  lea     rcx, [rbp+0B0h+arg_0]
0x180014233  mov     [rsp+1B0h+var_180], rcx; unsigned int *
0x180014238  lea     rcx, [rbp+0B0h+var_B0]
0x18001423c  mov     [rsp+1B0h+var_188], rcx; unsigned __int8 **
0x180014241  mov     dword ptr [rsp+1B0h+var_190], 2; unsigned int
0x180014249  mov     r9, rax; unsigned __int16 *
0x18001424c  mov     r8, rbx; unsigned __int16 *
0x18001424f  xor     edx, edx; HKEY
0x180014251  lea     rcx, [rbp+0B0h+var_B8]; this
0x180014255  call    ?ReadBufferFromRegistry@RegistryHelper@@QEAAJPEAUHKEY__@@PEBG1KPEAPEAEPEAK@Z; RegistryHelper::ReadBufferFromRegistry(HKEY__ *,ushort const *,ushort const *,ulong,uchar * *,ulong *)
0x18001425a  mov     [rsp+1B0h+var_140], eax
0x18001425e  test    eax, eax
0x180014260  jns     short loc_180014279
0x180014262  lea     rcx, aHrRegistryhelp_6; "hr = registryHelper.ReadBufferFromRegis"...
0x180014269  mov     [rsp+1B0h+var_190], rcx
0x18001426e  mov     r8d, 38Dh
0x180014274  jmp     loc_1800141D1
0x180014279  cmp     [rbp+0B0h+arg_0], edi
0x18001427f  jnz     short loc_1800142A6
0x180014281  mov     r14d, 80070002h
0x180014287  mov     [rsp+1B0h+var_140], r14d
0x18001428c  lea     rax, aDefaultidbuffe; "defaultIdBufferSize != 0"
0x180014293  mov     [rsp+1B0h+var_190], rax
0x180014298  mov     r9d, r14d
0x18001429b  mov     r8d, 38Fh
0x1800142a1  jmp     loc_1800141D4
0x1800142a6  mov     rdx, [rbp+0B0h+var_B0]
0x1800142aa  lea     rcx, [rbp+0B0h+var_120]
0x1800142ae  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800142b3  mov     edx, esi
0x1800142b5  call    ?GetIdentityTokenKey@IdentityStorage@@AEAAPEBGW4_ModernIdentityType@@@Z; IdentityStorage::GetIdentityTokenKey(_ModernIdentityType)
0x1800142ba  mov     rdx, rax
0x1800142bd  lea     rcx, [rbp+0B0h+var_110]
0x1800142c1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800142c6  jmp     loc_180014686
0x1800142cb  mov     rcx, [r15]
0x1800142ce  mov     rax, [rcx]
0x1800142d1  mov     rax, [rax+8]
0x1800142d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142da  mov     rsi, rax
0x1800142dd  mov     [rbp+0B0h+var_F8], rdi
0x1800142e1  mov     qword ptr [rbp+0B0h+var_E8], rax
0x1800142e5  mov     [rbp+0B0h+var_F8+8], rdi
0x1800142e9  mov     [rbp+0B0h+var_98], rdi
0x1800142ed  mov     [rbp+0B0h+var_88], rax
0x1800142f1  mov     [rbp+0B0h+var_90], rdi
0x1800142f5  lea     r8, aSoftwareMicros_5; "Software\\Microsoft\\IdentityCRL\\Immer"...
0x1800142fc  lea     rdx, [rbp+0B0h+var_130]
0x180014300  mov     rcx, r15
0x180014303  call    ?GetEnvironmentSpecificRegistryKey@IdentityStorage@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; IdentityStorage::GetEnvironmentSpecificRegistryKey(ushort const *)
0x180014308  nop
0x180014309  mov     r8, r14
0x18001430c  mov     rdx, rax
0x18001430f  lea     rcx, [rsp+1B0h+Time]
0x180014314  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@0@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180014319  nop
0x18001431a  lea     rcx, [rbp+0B0h+var_130]; void *
0x18001431e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180014323  mov     [rbp+0B0h+var_118], edi
0x180014326  mov     [rbp+0B0h+var_128], edi
0x180014329  mov     [rbp+0B0h+var_C0], 0FFFFFFFF80000001h
0x180014331  lea     rax, [rbp+0B0h+var_F8]
0x180014335  mov     [rsp+1B0h+var_190], rax; HKEY *
0x18001433a  lea     r9, [rbp+0B0h+arg_0]; bool *
0x180014341  lea     r8, [rbp+0B0h+var_C0]; HKEY *
0x180014345  mov     rdx, rsi; struct IRegistryFunctions *
0x180014348  call    ?GetRootKey@RegistryHelper@@QEAAJPEAVIRegistryFunctions@@AEBQEAUHKEY__@@PEA_NPEAPEAU3@@Z; RegistryHelper::GetRootKey(IRegistryFunctions *,HKEY__ * const &,bool *,HKEY__ * *)
0x18001434d  mov     [rsp+1B0h+var_140], eax
0x180014351  test    eax, eax
0x180014353  jns     short loc_18001436F
0x180014355  lea     rcx, aHrRegistryhelp_3; "hr = registryHelper.GetRootKey(pRegistr"...
0x18001435c  mov     [rsp+1B0h+var_190], rcx
0x180014361  mov     r9d, eax
0x180014364  mov     r8d, 3A1h
0x18001436a  jmp     loc_1800149E6
0x18001436f  mov     rax, [rsi]
0x180014372  lea     rcx, [rbp+0B0h+var_98]
0x180014376  mov     [rsp+1B0h+var_188], rcx
0x18001437b  mov     dword ptr [rsp+1B0h+var_190], 20019h
0x180014383  xor     r9d, r9d
0x180014386  mov     r8, [rsp+1B0h+Time]
0x18001438b  mov     rdx, [rbp+0B0h+var_F8]
0x18001438f  mov     rcx, rsi
0x180014392  mov     rax, [rax+50h]
0x180014396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001439b  mov     r14d, 80070000h
0x1800143a1  test    eax, eax
0x1800143a3  jz      short loc_1800143CF
0x1800143a5  jle     short loc_1800143AD
0x1800143a7  movzx   eax, ax
0x1800143aa  or      eax, r14d
0x1800143ad  mov     [rsp+1B0h+var_140], eax
0x1800143b1  test    eax, eax
0x1800143b3  jns     short loc_1800143CF
0x1800143b5  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x1800143bc  mov     [rsp+1B0h+var_190], rcx
0x1800143c1  mov     r9d, eax
0x1800143c4  mov     r8d, 3A8h
0x1800143ca  jmp     loc_1800149E6
0x1800143cf  mov     rax, [rsi]
0x1800143d2  mov     [rsp+1B0h+var_150], rdi
0x1800143d7  mov     [rsp+1B0h+var_158], rdi
0x1800143dc  mov     [rsp+1B0h+var_160], rdi
0x1800143e1  lea     rcx, [rbp+0B0h+var_128]
0x1800143e5  mov     [rsp+1B0h+var_168], rcx
0x1800143ea  lea     rcx, [rbp+0B0h+var_118]
0x1800143ee  mov     [rsp+1B0h+var_170], rcx
0x1800143f3  mov     [rsp+1B0h+var_178], rdi
0x1800143f8  mov     [rsp+1B0h+var_180], rdi
0x1800143fd  mov     [rsp+1B0h+var_188], rdi
0x180014402  mov     [rsp+1B0h+var_190], rdi
0x180014407  xor     r9d, r9d
0x18001440a  xor     r8d, r8d
0x18001440d  mov     rdx, [rbp+0B0h+var_98]
0x180014411  mov     rcx, rsi
0x180014414  mov     rax, [rax+60h]
0x180014418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001441d  test    eax, eax
0x18001441f  jz      short loc_18001444B
0x180014421  jle     short loc_180014429
0x180014423  movzx   eax, ax
0x180014426  or      eax, r14d
0x180014429  mov     [rsp+1B0h+var_140], eax
0x18001442d  test    eax, eax
0x18001442f  jns     short loc_18001444B
0x180014431  lea     rcx, aHrHresultFromW_4; "hr = HRESULT_FROM_WIN32(LOCAL_STATUS)"
0x180014438  mov     [rsp+1B0h+var_190], rcx
0x18001443d  mov     r9d, eax
0x180014440  mov     r8d, 3B6h
0x180014446  jmp     loc_1800149E6
0x18001444b  inc     [rbp+0B0h+var_128]
0x18001444e  mov     r14d, edi
0x180014451  cmp     [rbp+0B0h+var_118], edi
0x180014454  jbe     loc_18001464E
0x18001445a  lea     rcx, [rbp+0B0h+var_130]; void *
0x18001445e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180014463  nop
0x180014464  mov     edx, [rbp+0B0h+var_128]
0x180014467  mov     [rbp+0B0h+arg_0], edx
0x18001446d  mov     rax, [rsi]
0x180014470  mov     rdi, [rax+88h]
0x180014477  lea     rcx, [rbp+0B0h+var_130]
0x18001447b  call    ?GetBufferSetLength@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::GetBufferSetLength(int)
0x180014480  xor     ecx, ecx
0x180014482  mov     [rsp+1B0h+var_170], rcx
0x180014487  mov     [rsp+1B0h+var_178], rcx
0x18001448c  mov     [rsp+1B0h+var_180], rcx
0x180014491  mov     [rsp+1B0h+var_188], rcx
0x180014496  lea     rcx, [rbp+0B0h+arg_0]
0x18001449d  mov     [rsp+1B0h+var_190], rcx
0x1800144a2  mov     r9, rax
0x1800144a5  mov     r8d, r14d
0x1800144a8  mov     rdx, [rbp+0B0h+var_98]
0x1800144ac  mov     rcx, rsi
0x1800144af  mov     rax, rdi
0x1800144b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144b7  mov     edi, eax
0x1800144b9  mov     edx, [rbp+0B0h+arg_0]
0x1800144bf  lea     rcx, [rbp+0B0h+var_130]
0x1800144c3  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
  ... truncated ...
```
