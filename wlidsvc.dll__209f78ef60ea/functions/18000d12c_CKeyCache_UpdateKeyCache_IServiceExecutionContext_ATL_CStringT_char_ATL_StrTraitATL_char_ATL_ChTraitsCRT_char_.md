# CKeyCache::UpdateKeyCache(IServiceExecutionContext *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)

- ea: `0x18000d12c`
- end: `0x18000d5f7`
- name: `?UpdateKeyCache@CKeyCache@@IEAAJPEAVIServiceExecutionContext@@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@11@Z`
- size: `1227`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014a20`

## callees

- `0x18000c050`
- `0x18000d12c`
- `0x18000d600`
- `0x18000d764`
- `0x18000d89c`
- `0x18000dd38`
- `0x18000dec4`
- `0x18000dfcc`
- `0x18000e008`
- `0x18000e0f0`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015fb0`
- `0x1800179c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180046c44`
- `0x18004d324`
- `0x1800872e4`
- `0x1801094f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d21a`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d2b8`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d413`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d4f7`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d21a`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d2b8`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d413`
- `api-ms-win-crt-private-l1-1-0!_o__mbsicmp` at `0x18000d4f7`

## string_xrefs

- `0x18000d192`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d1b5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d26b`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d2e4`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d3ed`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d4a7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d55d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d5a8`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d5da`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x18000d16b`: `CKeyCache::UpdateKeyCache`
- `0x18000d5d3`: `CKeyCache::UpdateKeyCache`
- `0x18000d25e`: `KeyCacheUpdate for purpose='%hs', version='%hs', material is empty=%d`
- `0x18000d550`: `Key '%hs' for '%hs' is updated.`
- `0x18000d59b`: `Unexpected error in UpdateKeyInRegistry: hr = 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CKeyCache::UpdateKeyCache(
        __int64 a1,
        __int64 a2,
        const unsigned __int8 **a3,
        unsigned __int8 **a4,
        _QWORD *a5)
{
  unsigned int v9; // ebx
  const unsigned __int8 **v11; // rax
  int v12; // ebx
  _QWORD *v13; // r12
  unsigned int v14; // eax
  unsigned int v15; // r13d
  __int64 i; // rbx
  CKeyBag *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // r13d
  __int64 j; // rbx
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  int v26; // r9d
  int KeyLatestNoLock; // eax
  int v28; // eax
  int v29; // ecx
  __int64 v30; // rax
  int updated; // eax
  CUserKey *v32; // [rsp+20h] [rbp-E0h]
  CUserKey *v33; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *Str2; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 *Str1; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v36[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+60h] [rbp-A0h]
  int v38; // [rsp+98h] [rbp-68h]
  _QWORD v39[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v40[128]; // [rsp+C0h] [rbp-40h] BYREF
  int v41; // [rsp+158h] [rbp+58h]
  int v42; // [rsp+160h] [rbp+60h] BYREF

  v41 = a2;
  CKeyBag::CKeyBag((CKeyBag *)v36);
  v42 = 0;
  v39[0] = "CKeyCache::UpdateKeyCache";
  v39[1] = &v42;
  v39[2] = 0;
  v39[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
    "CKeyCache::UpdateKeyCache",
    (const char *)0x156,
    0,
    (const unsigned __int16 *)v32);
  if ( *((_DWORD *)*a3 - 4) && *((_DWORD *)*a4 - 4) )
  {
    v11 = (const unsigned __int8 **)ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                                      &Str2,
                                      L"CredentialKey");
    v12 = _mbsicmp(*a3, *v11);
    ATL::CStringData::Release((ATL::CStringData *)(Str2 - 24));
    v13 = a5;
    if ( v12 )
    {
      updated = CKeyCache::UpdateKeyInRegistry(a1, a2, a3, a4, a5);
      if ( updated < 0 )
      {
        LODWORD(v33) = updated;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
          0x16Au,
          L"Unexpected error in UpdateKeyInRegistry: hr = 0x%x",
          v33);
      }
    }
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
      0x16Eu,
      L"KeyCacheUpdate for purpose='%hs', version='%hs', material is empty=%d",
      *a3,
      *a4,
      *(_DWORD *)(*v13 - 16LL) == 0);
    Str2 = (unsigned __int8 *)*a3;
    v14 = ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>::Hash(Str2);
    v15 = v14;
    if ( *(_QWORD *)a1 )
    {
      for ( i = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (v14 % *(_DWORD *)(a1 + 16))); i; i = *(_QWORD *)(i + 88) )
      {
        if ( *(_DWORD *)(i + 96) == v15 && !_mbsicmp(*(const unsigned __int8 **)i, Str2) )
          goto LABEL_13;
      }
    }
    i = 0;
LABEL_13:
    if ( !i )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
        0x174u,
        L"Creating keybag for purpose: '%hs'.",
        *a3);
      v17 = CKeyBag::CKeyBag((CKeyBag *)v40);
      v18 = ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CKeyBag,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CKeyBag>>::operator[](
              a1,
              *a3);
      CKeyBag::operator=(v18, v17);
      ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::RemoveAll(v40);
    }
    v19 = ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CKeyBag,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CKeyBag>>::operator[](
            a1,
            *a3);
    CKeyBag::operator=(v36, v19);
    Str2 = *a4;
    v20 = ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>::Hash(Str2);
    v21 = v20;
    if ( v36[0] )
    {
      for ( j = *(_QWORD *)(v36[0] + 8LL * (v20 % v37)); j; j = *(_QWORD *)(j + 24) )
      {
        if ( *(_DWORD *)(j + 32) == v21 && !_mbsicmp(*(const unsigned __int8 **)j, Str2) )
          goto LABEL_19;
      }
    }
    j = 0;
LABEL_19:
    if ( !j )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str2);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str1);
      ATL::CSimpleStringT<char,0>::operator=(&Str1, a4);
      ATL::CSimpleStringT<char,0>::operator=(&Str2, v13);
      v25 = ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::operator[](
              v36,
              *a4);
      CUserKey::operator=(v25, &Str2);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str1);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str2);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
        0x17Eu,
        L"Adding a new key for purpose: '%hs', version='%hs'",
        *a3,
        *a4);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str2);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str1);
      KeyLatestNoLock = CKeyCache::GetKeyLatestNoLock(a1, v41, (int)a3, v26, (CUserKey *)&Str2);
      v42 = KeyLatestNoLock;
      if ( KeyLatestNoLock < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
          "CKeyCache::UpdateKeyCache",
          0x182u,
          KeyLatestNoLock,
          "hr = GetKeyLatestNoLock(pExecutionContext, strPurpose, FALSE, latestKey)");
        RegionalPolicies::Headers::~Headers((RegionalPolicies::Headers *)&Str2);
        goto LABEL_3;
      }
      v28 = _mbsicmp(Str1, *a4);
      v29 = v38;
      if ( v28 <= 0 )
      {
        v29 = v38 | 1;
        v38 |= 1u;
      }
      if ( *(_DWORD *)(*v13 - 16LL) )
        v38 = v29 | 2;
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str1);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&Str2);
      goto LABEL_32;
    }
    if ( !*(_DWORD *)(*(_QWORD *)ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::operator[](
                                   v36,
                                   *a4)
                    - 16LL)
      && *(_DWORD *)(*v13 - 16LL) )
    {
      v23 = CUserKey::CUserKey(&Str2, a4, v13);
      v24 = ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::operator[](
              v36,
              *a4);
      CUserKey::operator=(v24, v23);
      RegionalPolicies::Headers::~Headers((RegionalPolicies::Headers *)&Str2);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
        0x19Du,
        L"Adding a key material for purpose: '%hs', version='%hs'",
        *a3,
        *a4);
      v38 |= 2u;
LABEL_32:
      v30 = ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CKeyBag,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CKeyBag>>::operator[](
              a1,
              *a3);
      CKeyBag::operator=(v30, v36);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
        0x1A4u,
        L"Key '%hs' for '%hs' is updated.",
        *a4,
        *a3);
    }
  }
  else
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\keycache.cpp",
      0x15Du,
      L"invalid argument, ignore this key.");
  }
LABEL_3:
  v9 = v42;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v39);
  ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::RemoveAll(v36);
  return v9;
}

```

## disassembly

```asm
0x18000d12c  mov     [rsp-8+arg_0], rbx
0x18000d131  mov     qword ptr [rsp-8+arg_8], rdx
0x18000d136  push    rbp
0x18000d137  push    rsi
0x18000d138  push    rdi
0x18000d139  push    r12
0x18000d13b  push    r13
0x18000d13d  push    r14
0x18000d13f  push    r15
0x18000d141  lea     rbp, [rsp-10h]
0x18000d146  sub     rsp, 110h
0x18000d14d  mov     rdi, r9
0x18000d150  mov     rsi, r8
0x18000d153  mov     r14, rdx
0x18000d156  mov     r15, rcx
0x18000d159  lea     rcx, [rsp+140h+var_F0]; this
0x18000d15e  call    ??0CKeyBag@@QEAA@XZ; CKeyBag::CKeyBag(void)
0x18000d163  nop
0x18000d164  xor     r13d, r13d
0x18000d167  mov     [rbp+40h+arg_10], r13d
0x18000d16b  lea     rcx, aCkeycacheUpdat_0; "CKeyCache::UpdateKeyCache"
0x18000d172  mov     [rbp+40h+var_A0], rcx
0x18000d176  lea     rax, [rbp+40h+arg_10]
0x18000d17a  mov     [rbp+40h+var_98], rax
0x18000d17e  mov     [rbp+40h+var_90], r13
0x18000d182  mov     [rbp+40h+var_88], r13
0x18000d186  xor     r9d, r9d; unsigned int
0x18000d189  mov     r8d, 156h; char *
0x18000d18f  mov     rdx, rcx; char *
0x18000d192  lea     rcx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d199  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000d19e  nop
0x18000d19f  mov     rax, [rsi]
0x18000d1a2  cmp     [rax-10h], r13d
0x18000d1a6  jnz     short loc_18000D1FA
0x18000d1a8  lea     r9, aInvalidArgumen; "invalid argument, ignore this key."
0x18000d1af  mov     r8d, 15Dh; unsigned int
0x18000d1b5  lea     rdx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d1bc  mov     ecx, 5; unsigned __int8
0x18000d1c1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d1c6  mov     ebx, [rbp+40h+arg_10]
0x18000d1c9  lea     rcx, [rbp+40h+var_A0]
0x18000d1cd  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000d1d2  nop
0x18000d1d3  lea     rcx, [rsp+140h+var_F0]
0x18000d1d8  call    ?RemoveAll@?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCUserKey@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCUserKey@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::RemoveAll(void)
0x18000d1dd  mov     eax, ebx
0x18000d1df  mov     rbx, [rsp+140h+arg_0]
0x18000d1e7  add     rsp, 110h
0x18000d1ee  pop     r15
0x18000d1f0  pop     r14
0x18000d1f2  pop     r13
0x18000d1f4  pop     r12
0x18000d1f6  pop     rdi
0x18000d1f7  pop     rsi
0x18000d1f8  pop     rbp
0x18000d1f9  retn
0x18000d1fa  mov     rax, [rdi]
0x18000d1fd  cmp     [rax-10h], r13d
0x18000d201  jz      short loc_18000D1A8
0x18000d203  lea     rdx, aCredentialkey; "CredentialKey"
0x18000d20a  lea     rcx, [rsp+140h+Str2]
0x18000d20f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18000d214  mov     rdx, [rax]; Str2
0x18000d217  mov     rcx, [rsi]; Str1
0x18000d21a  call    cs:__imp__mbsicmp
0x18000d220  mov     ebx, eax
0x18000d222  mov     rcx, [rsp+140h+Str2]
0x18000d227  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000d22b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000d230  mov     r12, [rbp+40h+arg_20]
0x18000d234  test    ebx, ebx
0x18000d236  jnz     loc_18000D579
0x18000d23c  mov     rax, [r12]
0x18000d240  mov     ecx, r13d
0x18000d243  cmp     [rax-10h], r13d
0x18000d247  setz    cl
0x18000d24a  mov     [rsp+140h+var_110], ecx
0x18000d24e  mov     rax, [rdi]
0x18000d251  mov     [rsp+140h+var_118], rax
0x18000d256  mov     rax, [rsi]
0x18000d259  mov     [rsp+140h+var_120], rax
0x18000d25e  lea     r9, aKeycacheupdate; "KeyCacheUpdate for purpose='%hs', versi"...
0x18000d265  mov     r8d, 16Eh; unsigned int
0x18000d26b  lea     rdx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d272  mov     r14d, 5
0x18000d278  mov     ecx, r14d; unsigned __int8
0x18000d27b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d280  mov     rax, [rsi]
0x18000d283  mov     [rsp+140h+Str2], rax
0x18000d288  mov     rcx, rax
0x18000d28b  call    ?Hash@?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@ATL@@SAKPEBD@Z; ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>::Hash(char const *)
0x18000d290  mov     r13d, eax
0x18000d293  mov     rbx, [r15]
0x18000d296  test    rbx, rbx
0x18000d299  jz      short loc_18000D2C8
0x18000d29b  xor     edx, edx
0x18000d29d  div     dword ptr [r15+10h]
0x18000d2a1  mov     rbx, [rbx+rdx*8]
0x18000d2a5  test    rbx, rbx
0x18000d2a8  jz      short loc_18000D2C8
0x18000d2aa  cmp     [rbx+60h], r13d
0x18000d2ae  jnz     short loc_18000D2C2
0x18000d2b0  mov     rdx, [rsp+140h+Str2]; Str2
0x18000d2b5  mov     rcx, [rbx]; Str1
0x18000d2b8  call    cs:__imp__mbsicmp
0x18000d2be  test    eax, eax
0x18000d2c0  jz      short loc_18000D2CA
0x18000d2c2  mov     rbx, [rbx+58h]
0x18000d2c6  jmp     short loc_18000D2A5
0x18000d2c8  xor     ebx, ebx
0x18000d2ca  test    rbx, rbx
0x18000d2cd  jnz     short loc_18000D31F
0x18000d2cf  mov     rax, [rsi]
0x18000d2d2  mov     [rsp+140h+var_120], rax
0x18000d2d7  lea     r9, aCreatingKeybag; "Creating keybag for purpose: '%hs'."
0x18000d2de  mov     r8d, 174h; unsigned int
0x18000d2e4  lea     rdx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d2eb  mov     ecx, r14d; unsigned __int8
0x18000d2ee  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d2f3  lea     rcx, [rbp+40h+var_80]; this
0x18000d2f7  call    ??0CKeyBag@@QEAA@XZ; CKeyBag::CKeyBag(void)
0x18000d2fc  mov     rbx, rax
0x18000d2ff  mov     rdx, [rsi]
0x18000d302  mov     rcx, r15
0x18000d305  call    ??A?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCKeyBag@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCKeyBag@@@2@@ATL@@QEAAAEAVCKeyBag@@PEBD@Z; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CKeyBag,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CKeyBag>>::operator[](char const *)
0x18000d30a  mov     rcx, rax
0x18000d30d  mov     rdx, rbx
0x18000d310  call    ??4CKeyBag@@QEAAAEAV0@AEBV0@@Z; CKeyBag::operator=(CKeyBag const &)
0x18000d315  nop
0x18000d316  lea     rcx, [rbp+40h+var_80]
0x18000d31a  call    ?RemoveAll@?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCUserKey@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCUserKey@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::RemoveAll(void)
0x18000d31f  mov     rdx, [rsi]
0x18000d322  mov     rcx, r15
0x18000d325  call    ??A?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCKeyBag@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCKeyBag@@@2@@ATL@@QEAAAEAVCKeyBag@@PEBD@Z; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CKeyBag,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CKeyBag>>::operator[](char const *)
0x18000d32a  mov     rdx, rax
0x18000d32d  lea     rcx, [rsp+140h+var_F0]
0x18000d332  call    ??4CKeyBag@@QEAAAEAV0@AEBV0@@Z; CKeyBag::operator=(CKeyBag const &)
0x18000d337  mov     rax, [rdi]
0x18000d33a  mov     [rsp+140h+Str2], rax
0x18000d33f  mov     rcx, rax
0x18000d342  call    ?Hash@?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@ATL@@SAKPEBD@Z; ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>::Hash(char const *)
0x18000d347  mov     r13d, eax
0x18000d34a  mov     rbx, [rsp+140h+var_F0]
0x18000d34f  test    rbx, rbx
0x18000d352  jz      short loc_18000D367
0x18000d354  xor     edx, edx
0x18000d356  div     [rsp+140h+var_E0]
0x18000d35a  mov     rbx, [rbx+rdx*8]
0x18000d35e  test    rbx, rbx
0x18000d361  jnz     loc_18000D405
0x18000d367  xor     ebx, ebx
0x18000d369  test    rbx, rbx
0x18000d36c  jz      loc_18000D42A
0x18000d372  mov     rdx, [rdi]
0x18000d375  lea     rcx, [rsp+140h+var_F0]
0x18000d37a  call    ??A?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCUserKey@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCUserKey@@@2@@ATL@@QEAAAEAVCUserKey@@PEBD@Z; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::operator[](char const *)
0x18000d37f  mov     rcx, [rax]
0x18000d382  cmp     dword ptr [rcx-10h], 0
0x18000d386  jnz     loc_18000D1C6
0x18000d38c  mov     rax, [r12]
0x18000d390  cmp     dword ptr [rax-10h], 0
0x18000d394  jz      loc_18000D1C6
0x18000d39a  mov     r8, r12
0x18000d39d  mov     rdx, rdi
0x18000d3a0  lea     rcx, [rsp+140h+Str2]
0x18000d3a5  call    ??0CUserKey@@QEAA@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@0@Z; CUserKey::CUserKey(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x18000d3aa  mov     rbx, rax
0x18000d3ad  mov     rdx, [rdi]
0x18000d3b0  lea     rcx, [rsp+140h+var_F0]
0x18000d3b5  call    ??A?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCUserKey@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCUserKey@@@2@@ATL@@QEAAAEAVCUserKey@@PEBD@Z; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::operator[](char const *)
0x18000d3ba  mov     rcx, rax
0x18000d3bd  mov     rdx, rbx
0x18000d3c0  call    ??4CUserKey@@QEAAAEAV0@AEBV0@@Z; CUserKey::operator=(CUserKey const &)
0x18000d3c5  nop
0x18000d3c6  lea     rcx, [rsp+140h+Str2]; this
0x18000d3cb  call    ??1Headers@RegionalPolicies@@QEAA@XZ; RegionalPolicies::Headers::~Headers(void)
0x18000d3d0  mov     rax, [rdi]
0x18000d3d3  mov     [rsp+140h+var_118], rax
0x18000d3d8  mov     rax, [rsi]
0x18000d3db  mov     [rsp+140h+var_120], rax
0x18000d3e0  lea     r9, aAddingAKeyMate; "Adding a key material for purpose: '%hs"...
0x18000d3e7  mov     r8d, 19Dh; unsigned int
0x18000d3ed  lea     rdx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d3f4  mov     ecx, r14d; unsigned __int8
0x18000d3f7  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d3fc  or      [rbp+40h+var_A8], 2
0x18000d400  jmp     loc_18000D528
0x18000d405  cmp     [rbx+20h], r13d
0x18000d409  jnz     short loc_18000D421
0x18000d40b  mov     rdx, [rsp+140h+Str2]; Str2
0x18000d410  mov     rcx, [rbx]; Str1
0x18000d413  call    cs:__imp__mbsicmp
0x18000d419  test    eax, eax
0x18000d41b  jz      loc_18000D369
0x18000d421  mov     rbx, [rbx+18h]
0x18000d425  jmp     loc_18000D35E
0x18000d42a  lea     rcx, [rsp+140h+Str2]
0x18000d42f  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d434  nop
0x18000d435  lea     rcx, [rsp+140h+Str1]
0x18000d43a  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d43f  nop
0x18000d440  mov     rdx, rdi
0x18000d443  lea     rcx, [rsp+140h+Str1]
0x18000d448  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x18000d44d  mov     rdx, r12
0x18000d450  lea     rcx, [rsp+140h+Str2]
0x18000d455  call    ??4?$CSimpleStringT@D$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<char,0>::operator=(ATL::CSimpleStringT<char,0> const &)
0x18000d45a  nop
0x18000d45b  mov     rdx, [rdi]
0x18000d45e  lea     rcx, [rsp+140h+var_F0]
0x18000d463  call    ??A?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCUserKey@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCUserKey@@@2@@ATL@@QEAAAEAVCUserKey@@PEBD@Z; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CUserKey,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CUserKey>>::operator[](char const *)
0x18000d468  mov     rcx, rax
0x18000d46b  lea     rdx, [rsp+140h+Str2]
0x18000d470  call    ??4CUserKey@@QEAAAEAV0@AEBV0@@Z; CUserKey::operator=(CUserKey const &)
0x18000d475  nop
0x18000d476  lea     rcx, [rsp+140h+Str1]
0x18000d47b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d480  lea     rcx, [rsp+140h+Str2]
0x18000d485  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d48a  mov     rax, [rdi]
0x18000d48d  mov     [rsp+140h+var_118], rax
0x18000d492  mov     rax, [rsi]
0x18000d495  mov     [rsp+140h+var_120], rax
0x18000d49a  lea     r9, aAddingANewKeyF; "Adding a new key for purpose: '%hs', ve"...
0x18000d4a1  mov     r8d, 17Eh; unsigned int
0x18000d4a7  lea     rdx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d4ae  mov     ecx, r14d; unsigned __int8
0x18000d4b1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d4b6  lea     rcx, [rsp+140h+Str2]
0x18000d4bb  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d4c0  lea     rcx, [rsp+140h+Str1]
0x18000d4c5  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d4ca  nop
0x18000d4cb  lea     rax, [rsp+140h+Str2]
0x18000d4d0  mov     [rsp+140h+var_120], rax; CUserKey *
0x18000d4d5  mov     r8, rsi; int
0x18000d4d8  mov     rdx, qword ptr [rbp+40h+arg_8]; int
0x18000d4dc  mov     rcx, r15; int
0x18000d4df  call    ?GetKeyLatestNoLock@CKeyCache@@IEAAJPEAVIServiceExecutionContext@@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@HAEAVCUserKey@@@Z; CKeyCache::GetKeyLatestNoLock(IServiceExecutionContext *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,int,CUserKey &)
0x18000d4e4  mov     [rbp+40h+arg_10], eax
0x18000d4e7  test    eax, eax
0x18000d4e9  js      loc_18000D5BE
0x18000d4ef  mov     rdx, [rdi]; Str2
0x18000d4f2  mov     rcx, [rsp+140h+Str1]; Str1
0x18000d4f7  call    cs:__imp__mbsicmp
0x18000d4fd  mov     ecx, [rbp+40h+var_A8]
0x18000d500  test    eax, eax
0x18000d502  jg      short loc_18000D50A
0x18000d504  or      ecx, 1
0x18000d507  mov     [rbp+40h+var_A8], ecx
0x18000d50a  mov     rax, [r12]
0x18000d50e  cmp     dword ptr [rax-10h], 0
0x18000d512  jnz     short loc_18000D571
0x18000d514  lea     rcx, [rsp+140h+Str1]
0x18000d519  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d51e  lea     rcx, [rsp+140h+Str2]
0x18000d523  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18000d528  mov     rdx, [rsi]
0x18000d52b  mov     rcx, r15
0x18000d52e  call    ??A?$CAtlMap@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@VCKeyBag@@V?$CStringElementTraitsI@V?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@V?$CDefaultCharTraits@D@2@@2@V?$CElementTraits@VCKeyBag@@@2@@ATL@@QEAAAEAVCKeyBag@@PEBD@Z; ATL::CAtlMap<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,CKeyBag,ATL::CStringElementTraitsI<ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>,ATL::CDefaultCharTraits<char>>,ATL::CElementTraits<CKeyBag>>::operator[](char const *)
0x18000d533  mov     rcx, rax
0x18000d536  lea     rdx, [rsp+140h+var_F0]
0x18000d53b  call    ??4CKeyBag@@QEAAAEAV0@AEBV0@@Z; CKeyBag::operator=(CKeyBag const &)
0x18000d540  mov     rax, [rsi]
0x18000d543  mov     [rsp+140h+var_118], rax
0x18000d548  mov     rax, [rdi]
0x18000d54b  mov     [rsp+140h+var_120], rax
0x18000d550  lea     r9, aKeyHsForHsIsUp; "Key '%hs' for '%hs' is updated."
0x18000d557  mov     r8d, 1A4h; unsigned int
0x18000d55d  lea     rdx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d564  mov     ecx, r14d; unsigned __int8
0x18000d567  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d56c  jmp     loc_18000D1C6
0x18000d571  or      ecx, 2
0x18000d574  mov     [rbp+40h+var_A8], ecx
0x18000d577  jmp     short loc_18000D514
0x18000d579  mov     [rsp+140h+var_120], r12
0x18000d57e  mov     r9, rdi
0x18000d581  mov     r8, rsi
0x18000d584  mov     rdx, r14
0x18000d587  mov     rcx, r15
0x18000d58a  call    ?UpdateKeyInRegistry@CKeyCache@@AEAAJPEAVIServiceExecutionContext@@AEBV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@11@Z; CKeyCache::UpdateKeyInRegistry(IServiceExecutionContext *,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &,ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> const &)
0x18000d58f  test    eax, eax
0x18000d591  jns     loc_18000D23C
0x18000d597  mov     dword ptr [rsp+140h+var_120], eax
0x18000d59b  lea     r9, aUnexpectedErro; "Unexpected error in UpdateKeyInRegistry"...
0x18000d5a2  mov     r8d, 16Ah; unsigned int
0x18000d5a8  lea     rdx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d5af  mov     ecx, 2; unsigned __int8
0x18000d5b4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000d5b9  jmp     loc_18000D23C
0x18000d5be  lea     r8, aHrGetkeylatest_0; "hr = GetKeyLatestNoLock(pExecutionConte"...
0x18000d5c5  mov     [rsp+140h+var_120], r8; char *
0x18000d5ca  mov     r9d, eax; int
0x18000d5cd  mov     r8d, 182h; unsigned int
0x18000d5d3  lea     rdx, aCkeycacheUpdat_0; "CKeyCache::UpdateKeyCache"
0x18000d5da  lea     rcx, aOnecoreuapDsEx_53; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18000d5e1  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
  ... truncated ...
```
