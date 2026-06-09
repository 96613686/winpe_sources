# CleanupSystemStoreEntryForSid(ushort const *)

- ea: `0x18008e644`
- end: `0x18008ed2a`
- name: `?CleanupSystemStoreEntryForSid@@YAJPEBG@Z`
- size: `1766`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180098cb8`

## callees

- `0x18000baac`
- `0x18000c050`
- `0x18000e8dc`
- `0x18000ed04`
- `0x18000ed3c`
- `0x1800124c4`
- `0x18001426c`
- `0x1800143a4`
- `0x1800151c4`
- `0x180015860`
- `0x180018f80`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001f968`
- `0x180037bac`
- `0x180038a80`
- `0x180039d00`
- `0x18003eb54`
- `0x18003ec18`
- `0x180041ce8`
- `0x180043344`
- `0x1800801dc`
- `0x180081cac`
- `0x180084e88`
- `0x18008e644`
- `0x1800a3b60`
- `0x1800a4778`
- `0x1800a716c`
- `0x1800c30e8`
- `0x1800c4000`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e99b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008e99b`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18008e7db`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18008e7db`
- `ntdll!RtlReleaseResource` at `0x18008eca9`
- `ntdll!RtlReleaseResource` at `0x18008eca9`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008eb3c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18008eb3c`

## string_xrefs

- `0x18008e6f2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18008e71b`: `hr = client.ImpersonateClient()`
- `0x18008e9e7`: `Found Account %ls for SID %ls.`
- `0x18008ec27`: `hr = pStoredId->RemoveKeywords(CStringW(g_wszKeyword_Connected), fChanged, FALSE, eLocal)`
- `0x18008e761`: `hr = client.IsImpersonatingSystem(isSystem)`
- `0x18008e6ca`: `CleanupSystemStoreEntryForSid`
- `0x18008ea2f`: `CleanupSystemStoreEntryForSid`
- `0x18008ec96`: `CleanupSystemStoreEntryForSid`
- `0x18008e78c`: `hr = HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)`
- `0x18008ea5f`: `SID %ls not found in system store.`
- `0x18008eb7b`: `SID %ls is not Associated.`
- `0x18008ebb8`: `SID %ls is not Connected.`
- `0x18008ec81`: `hr = Transaction.Commit( nullptr, true)`

## pseudocode

```c
__int64 __fastcall CleanupSystemStoreEntryForSid(const unsigned __int16 *a1)
{
  int v2; // eax
  int IsImpersonatingSystem; // eax
  signed int v4; // r9d
  const char *v5; // rax
  unsigned int v6; // r8d
  LSTATUS v7; // eax
  HKEY v8; // r15
  int v9; // eax
  unsigned int v10; // r14d
  __int64 v11; // rbx
  signed int v12; // edi
  unsigned int v13; // edi
  int v14; // eax
  signed int v15; // r9d
  int v16; // eax
  unsigned int v17; // r8d
  void *v18; // rax
  int v19; // edi
  int v20; // ebx
  int v21; // eax
  volatile signed __int32 *v22; // rbx
  struct _RTL_RESOURCE *v23; // rdi
  int v24; // eax
  const char *v25; // rcx
  unsigned int v26; // r8d
  const unsigned __int16 *v27; // r9
  unsigned int v28; // r8d
  int v29; // eax
  int v30; // esi
  unsigned int v31; // ebx
  const unsigned __int16 *v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+30h] [rbp-D0h] BYREF
  volatile signed __int32 *v35; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v36[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h] BYREF
  volatile signed __int32 *v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult[2]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v43[3]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v44[3]; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v45[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v46[64]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v47[6]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v48[192]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v49[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v34 = 0;
  memset(v44, 0, sizeof(v44));
  memset(v43, 0, sizeof(v43));
  memset(v45, 0, 24);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  v40 = 0;
  v41 = 0;
  v36[0] = 0;
  phkResult[0] = 0;
  v47[0] = "CleanupSystemStoreEntryForSid";
  v47[1] = &v34;
  v47[2] = 0;
  v47[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "CleanupSystemStoreEntryForSid",
    (const char *)0x30E7,
    0,
    v33);
  v35 = 0;
  v2 = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v35, 0);
  v34 = v2;
  if ( v2 >= 0 )
  {
    IsImpersonatingSystem = CAutoImpersonateClient::IsImpersonatingSystem((CAutoImpersonateClient *)&v35, (int *)v36);
    v34 = IsImpersonatingSystem;
    if ( IsImpersonatingSystem < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "CleanupSystemStoreEntryForSid",
        0x30EEu,
        IsImpersonatingSystem,
        "hr = client.IsImpersonatingSystem(isSystem)");
      goto LABEL_3;
    }
    CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v35);
    if ( !v36[0] )
    {
      v4 = -2147023582;
      v5 = "hr = HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)";
      v6 = 12532;
LABEL_8:
      v34 = v4;
LABEL_9:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "CleanupSystemStoreEntryForSid",
        v6,
        v4,
        v5);
      goto LABEL_66;
    }
    if ( !a1 )
    {
      v4 = -2147024809;
      v5 = "hr = E_INVALIDARG";
      v6 = 12537;
      goto LABEL_8;
    }
    v7 = RegOpenCurrentUser(0x20019u, phkResult);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    v34 = v4;
    if ( v4 < 0 )
    {
      v5 = "hr = HRESULT_FROM_WIN32(regOpsStatus)";
      v6 = 12541;
      goto LABEL_9;
    }
    v8 = phkResult[0];
    v45[0] = phkResult[0];
    v9 = ATL::CRegKey::Open(
           (ATL::CRegKey *)v44,
           phkResult[0],
           L"Software\\Microsoft\\IdentityCRL\\StoredIdentities",
           0x20019u);
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    v34 = v4;
    if ( v4 < 0 )
    {
      v5 = "hr = HRESULT_FROM_WIN32(regOpsStatus)";
      v6 = 12549;
      goto LABEL_9;
    }
    v10 = 0;
    v11 = v38;
    while ( 2 )
    {
      v36[0] = 256;
      memset_0(v49, 0, 0x202u);
      v12 = ATL::CRegKey::EnumKey((ATL::CRegKey *)v44, v10, v49, v36, 0);
      if ( v12 != 259 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v35,
          v49,
          v36[0]);
        if ( v12 > 0 )
          v12 = (unsigned __int16)v12 | 0x80070000;
        v34 = v12;
        if ( v12 < 0 )
        {
          v15 = v12;
          v17 = 12572;
        }
        else
        {
          v13 = 0;
          ATL::CSimpleStringT<unsigned short,0>::SetString(&v39, L"Software\\Microsoft\\IdentityCRL\\StoredIdentities");
          ATL::CSimpleStringT<unsigned short,0>::Append(&v39, L"\\");
          ATL::CSimpleStringT<unsigned short,0>::Append(&v39, &v35);
          v14 = ATL::CRegKey::Open((ATL::CRegKey *)v43, v8, v39, 0x20019u);
          v15 = v14;
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
          v34 = v15;
          if ( v15 >= 0 )
          {
            while ( 1 )
            {
              memset_0(v48, 0, 0x176u);
              v37 = 187;
              v16 = ATL::CRegKey::EnumKey((ATL::CRegKey *)v43, v13, v48, &v37, 0);
              v15 = v16;
              if ( v16 == 259 )
                break;
              if ( v16 > 0 )
                v15 = (unsigned __int16)v16 | 0x80070000;
              v34 = v15;
              if ( v15 < 0 )
              {
                v17 = 12606;
                goto LABEL_41;
              }
              if ( !(unsigned int)_o__wcsicmp(a1, v48) )
              {
                ATL::CSimpleStringT<unsigned short,0>::operator=(&v38, &v35);
                v11 = v38;
                break;
              }
              ++v13;
            }
            if ( !*(_DWORD *)(v11 - 16) )
            {
              ++v10;
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
              continue;
            }
            TracePrintW(
              5u,
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              0x314Au,
              L"Found Account %ls for SID %ls.",
              v11,
              a1);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
            break;
          }
          v17 = 12585;
        }
LABEL_41:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "CleanupSystemStoreEntryForSid",
          v17,
          v15,
          "hr = HRESULT_FROM_WIN32(regOpsStatus)");
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v35);
        goto LABEL_66;
      }
      break;
    }
    if ( !*(_DWORD *)(v11 - 16) )
    {
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x3152u,
        L"SID %ls not found in system store.",
        a1);
      v34 = 1317;
    }
    v18 = operator new(0x120u, (const struct std::nothrow_t *)std::nothrow);
    v19 = (int)v18;
    *(_QWORD *)v36 = v18;
    if ( v18 )
    {
      v47[4] = &v35;
      v20 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v35,
              a1);
      v21 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v37,
              &v38);
      v22 = (volatile signed __int32 *)CStoredIdentity::CStoredIdentity(v19, v21, v20, (unsigned int)&v41, 0);
    }
    else
    {
      v22 = 0;
    }
    CAutoRefPtr<IStoredIdentity>::Deinit(&v40);
    v40 = v22;
    if ( !v22 )
    {
      v34 = -2147024882;
      goto LABEL_66;
    }
    v37 = 0;
    v35 = v22;
    _InterlockedIncrement(v22 + 2);
    CStoredIdentityTransaction::CStoredIdentityTransaction(v46, &v35);
    v23 = (struct _RTL_RESOURCE *)((char *)g_pPPCRL + 2136);
    phkResult[1] = (HKEY)((char *)g_pPPCRL + 2136);
    RtlAcquireResourceExclusive((PRTL_RESOURCE)((char *)g_pPPCRL + 2136), 1u);
    v24 = CStoredIdentityTransaction::Start((CStoredIdentityTransaction *)v46);
    v34 = v24;
    if ( v24 < 0 )
    {
      v25 = "hr = Transaction.Start()";
      v26 = 12640;
LABEL_64:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "CleanupSystemStoreEntryForSid",
        v26,
        v24,
        v25);
      goto LABEL_65;
    }
    if ( (*(unsigned int (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)v22 + 16LL))(v22, 0) )
    {
      if ( (*(unsigned int (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 24LL))(v22) )
      {
        v24 = CStoredIdentity::Disassociate((CStoredIdentity *)v22);
        v34 = v24;
        if ( v24 < 0 )
        {
          v25 = "hr = pStoredId->Disassociate()";
          v26 = 12659;
          goto LABEL_64;
        }
        v29 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v41,
                L"Connected");
        v30 = CStoredIdentity::RemoveKeywords((_DWORD)v22, v29, (unsigned int)&v37, 0, 0);
        v34 = v30;
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v41);
        if ( v30 >= 0 )
        {
          v24 = CStoredIdentity::SetProperty((CStoredIdentity *)v22, L"DefaultCredSaved", &qword_18013DE20);
          v34 = v24;
          if ( v24 < 0 )
          {
            v25 = "hr = pStoredId->SetProperty(PPCRL_CREDPROPERTY_DEFAULTCREDSAVED, L\"\")";
            v26 = 12663;
            goto LABEL_64;
          }
          v24 = CStoredIdentityTransaction::Commit((CStoredIdentityTransaction *)v46, 0, 1);
          v34 = v24;
          if ( v24 < 0 )
          {
            v25 = "hr = Transaction.Commit( nullptr, true)";
            v26 = 12667;
            goto LABEL_64;
          }
        }
        else
        {
          Telemetry::IfFailExit(
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            "CleanupSystemStoreEntryForSid",
            0x3175u,
            v30,
            "hr = pStoredId->RemoveKeywords(CStringW(g_wszKeyword_Connected), fChanged, FALSE, eLocal)");
        }
LABEL_65:
        RtlReleaseResource(v23);
        CStoredIdentityTransaction::~CStoredIdentityTransaction((CStoredIdentityTransaction *)v46);
        goto LABEL_66;
      }
      v27 = L"SID %ls is not Connected.";
      v28 = 12654;
    }
    else
    {
      v27 = L"SID %ls is not Associated.";
      v28 = 12646;
    }
    v34 = -2147186548;
    TracePrintW(5u, "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp", v28, v27, a1);
    goto LABEL_65;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "CleanupSystemStoreEntryForSid",
    0x30EDu,
    v2,
    "hr = client.ImpersonateClient()");
LABEL_3:
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v35);
LABEL_66:
  v31 = v34;
  CTraceFuncW<long>::~CTraceFuncW<long>(v47);
  CAutoRefPtr<IStoredIdentity>::Deinit(&v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v38);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v39);
  ATL::CRegKey::Close((ATL::CRegKey *)v45);
  ATL::CRegKey::Close((ATL::CRegKey *)v43);
  ATL::CRegKey::Close((ATL::CRegKey *)v44);
  return v31;
}

```

## disassembly

```asm
0x18008e644  push    rbp
0x18008e646  push    rbx
0x18008e647  push    rsi
0x18008e648  push    rdi
0x18008e649  push    r12
0x18008e64b  push    r13
0x18008e64d  push    r14
0x18008e64f  push    r15
0x18008e651  lea     rbp, [rsp-3E8h]
0x18008e659  sub     rsp, 4E8h
0x18008e660  mov     rax, cs:__security_cookie
0x18008e667  xor     rax, rsp
0x18008e66a  mov     [rbp+420h+var_50], rax
0x18008e671  mov     rsi, rcx
0x18008e674  xor     r12d, r12d
0x18008e677  mov     [rsp+520h+var_4F0], r12d
0x18008e67c  mov     [rbp+420h+var_488], r12
0x18008e680  mov     [rbp+420h+var_480], r12
0x18008e684  mov     [rbp+420h+var_478], r12
0x18008e688  mov     [rbp+420h+var_4A0], r12
0x18008e68c  mov     [rbp+420h+var_498], r12
0x18008e690  mov     [rbp+420h+var_490], r12
0x18008e694  mov     [rbp+420h+var_470], r12
0x18008e698  mov     [rbp+420h+var_468], r12
0x18008e69c  mov     [rbp+420h+var_460], r12
0x18008e6a0  lea     rcx, [rsp+520h+var_4C8]
0x18008e6a5  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008e6aa  nop
0x18008e6ab  lea     rcx, [rsp+520h+var_4D0]
0x18008e6b0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008e6b5  nop
0x18008e6b6  mov     [rsp+520h+var_4C0], r12
0x18008e6bb  mov     [rsp+520h+var_4B8], r12
0x18008e6c0  mov     [rsp+520h+var_4E0], r12d
0x18008e6c5  mov     [rsp+520h+phkResult], r12
0x18008e6ca  lea     rbx, aCleanupsystems; "CleanupSystemStoreEntryForSid"
0x18008e6d1  mov     [rbp+420h+var_410], rbx
0x18008e6d5  lea     rax, [rsp+520h+var_4F0]
0x18008e6da  mov     [rbp+420h+var_408], rax
0x18008e6de  mov     [rbp+420h+var_400], r12
0x18008e6e2  mov     [rbp+420h+var_3F8], r12
0x18008e6e6  xor     r9d, r9d; unsigned int
0x18008e6e9  mov     r8d, 30E7h; char *
0x18008e6ef  mov     rdx, rbx; char *
0x18008e6f2  lea     r13, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18008e6f9  mov     rcx, r13; this
0x18008e6fc  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18008e701  nop
0x18008e702  mov     [rsp+520h+var_4E8], r12
0x18008e707  xor     edx, edx; struct ATL::CAccessToken *
0x18008e709  lea     rcx, [rsp+520h+var_4E8]; this
0x18008e70e  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x18008e713  mov     [rsp+520h+var_4F0], eax
0x18008e717  test    eax, eax
0x18008e719  jns     short loc_18008E74A
0x18008e71b  lea     r8, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x18008e722  mov     [rsp+520h+var_500], r8; char *
0x18008e727  mov     r8d, 30EDh; unsigned int
0x18008e72d  mov     r9d, eax; int
0x18008e730  mov     rdx, rbx; char *
0x18008e733  mov     rcx, r13; char *
0x18008e736  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18008e73b  lea     rcx, [rsp+520h+var_4E8]; this
0x18008e740  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x18008e745  jmp     loc_18008ECB9
0x18008e74a  lea     rdx, [rsp+520h+var_4E0]; int *
0x18008e74f  lea     rcx, [rsp+520h+var_4E8]; this
0x18008e754  call    ?IsImpersonatingSystem@CAutoImpersonateClient@@QEAAJAEAH@Z; CAutoImpersonateClient::IsImpersonatingSystem(int &)
0x18008e759  mov     [rsp+520h+var_4F0], eax
0x18008e75d  test    eax, eax
0x18008e75f  jns     short loc_18008E775
0x18008e761  lea     rcx, aHrClientIsimpe; "hr = client.IsImpersonatingSystem(isSys"...
0x18008e768  mov     [rsp+520h+var_500], rcx
0x18008e76d  mov     r8d, 30EEh
0x18008e773  jmp     short loc_18008E72D
0x18008e775  lea     rcx, [rsp+520h+var_4E8]; this
0x18008e77a  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x18008e77f  cmp     [rsp+520h+var_4E0], r12d
0x18008e784  jnz     short loc_18008E7B3
0x18008e786  mov     r9d, 80070522h; int
0x18008e78c  lea     rax, aHrHresultFromW_0; "hr = HRESULT_FROM_WIN32(ERROR_PRIVILEGE"...
0x18008e793  mov     r8d, 30F4h; unsigned int
0x18008e799  mov     [rsp+520h+var_4F0], r9d
0x18008e79e  mov     [rsp+520h+var_500], rax; char *
0x18008e7a3  mov     rdx, rbx; char *
0x18008e7a6  mov     rcx, r13; char *
0x18008e7a9  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18008e7ae  jmp     loc_18008ECB9
0x18008e7b3  test    rsi, rsi
0x18008e7b6  jnz     short loc_18008E7CD
0x18008e7b8  mov     r9d, 80070057h
0x18008e7be  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x18008e7c5  mov     r8d, 30F9h
0x18008e7cb  jmp     short loc_18008E799
0x18008e7cd  lea     rdx, [rsp+520h+phkResult]; phkResult
0x18008e7d2  mov     r14d, 20019h
0x18008e7d8  mov     ecx, r14d; samDesired
0x18008e7db  call    cs:__imp_RegOpenCurrentUser
0x18008e7e1  mov     r9d, eax
0x18008e7e4  mov     edi, 80070000h
0x18008e7e9  test    eax, eax
0x18008e7eb  jle     short loc_18008E7F4
0x18008e7ed  movzx   r9d, ax
0x18008e7f1  or      r9d, edi
0x18008e7f4  mov     [rsp+520h+var_4F0], r9d
0x18008e7f9  test    r9d, r9d
0x18008e7fc  jns     short loc_18008E80D
0x18008e7fe  lea     rax, aHrHresultFromW_9; "hr = HRESULT_FROM_WIN32(regOpsStatus)"
0x18008e805  mov     r8d, 30FDh
0x18008e80b  jmp     short loc_18008E79E
0x18008e80d  mov     r15, [rsp+520h+phkResult]
0x18008e812  mov     [rbp+420h+var_470], r15
0x18008e816  mov     r9d, r14d; unsigned int
0x18008e819  lea     r8, aSoftwareMicros_20; "Software\\Microsoft\\IdentityCRL\\Store"...
0x18008e820  mov     rdx, r15; HKEY
0x18008e823  lea     rcx, [rbp+420h+var_488]; this
0x18008e827  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18008e82c  mov     r9d, eax
0x18008e82f  test    eax, eax
0x18008e831  jle     short loc_18008E83A
0x18008e833  movzx   r9d, ax
0x18008e837  or      r9d, edi
0x18008e83a  mov     [rsp+520h+var_4F0], r9d
0x18008e83f  test    r9d, r9d
0x18008e842  jns     short loc_18008E856
0x18008e844  lea     rax, aHrHresultFromW_9; "hr = HRESULT_FROM_WIN32(regOpsStatus)"
0x18008e84b  mov     r8d, 3105h
0x18008e851  jmp     loc_18008E79E
0x18008e856  mov     r14d, r12d
0x18008e859  mov     rbx, [rsp+520h+var_4D0]
0x18008e85e  mov     [rsp+520h+var_4E0], 100h
0x18008e866  xor     edx, edx; Val
0x18008e868  mov     r8d, 202h; Size
0x18008e86e  lea     rcx, [rbp+420h+var_260]; void *
0x18008e875  call    memset_0
0x18008e87a  mov     [rsp+520h+var_500], r12; PFILETIME
0x18008e87f  lea     r9, [rsp+520h+var_4E0]; unsigned int *
0x18008e884  lea     r8, [rbp+420h+var_260]; unsigned __int16 *
0x18008e88b  mov     edx, r14d; unsigned int
0x18008e88e  lea     rcx, [rbp+420h+var_488]; this
0x18008e892  call    ?EnumKey@CRegKey@ATL@@QEAAJKPEAGPEAKPEAU_FILETIME@@@Z; ATL::CRegKey::EnumKey(ulong,ushort *,ulong *,_FILETIME *)
0x18008e897  mov     edi, eax
0x18008e899  cmp     eax, 103h
0x18008e89e  jz      loc_18008EA4E
0x18008e8a4  mov     r8d, [rsp+520h+var_4E0]
0x18008e8a9  lea     rdx, [rbp+420h+var_260]
0x18008e8b0  lea     rcx, [rsp+520h+var_4E8]
0x18008e8b5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *,int)
0x18008e8ba  nop
0x18008e8bb  test    edi, edi
0x18008e8bd  jle     short loc_18008E8C8
0x18008e8bf  movzx   edi, di
0x18008e8c2  or      edi, 80070000h
0x18008e8c8  mov     [rsp+520h+var_4F0], edi
0x18008e8cc  test    edi, edi
0x18008e8ce  js      loc_18008EA1A
0x18008e8d4  mov     edi, r12d
0x18008e8d7  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\IdentityCRL\\Store"...
0x18008e8de  lea     rcx, [rsp+520h+var_4C8]
0x18008e8e3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18008e8e8  lea     rdx, SubBlock; "\\"
0x18008e8ef  lea     rcx, [rsp+520h+var_4C8]
0x18008e8f4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18008e8f9  lea     rdx, [rsp+520h+var_4E8]
0x18008e8fe  lea     rcx, [rsp+520h+var_4C8]
0x18008e903  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<ushort,0>::Append(ATL::CSimpleStringT<ushort,0> const &)
0x18008e908  mov     r9d, 20019h; unsigned int
0x18008e90e  mov     r8, [rsp+520h+var_4C8]; unsigned __int16 *
0x18008e913  mov     rdx, r15; HKEY
0x18008e916  lea     rcx, [rbp+420h+var_4A0]; this
0x18008e91a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18008e91f  mov     r9d, eax
0x18008e922  test    eax, eax
0x18008e924  jle     short loc_18008E931
0x18008e926  movzx   r9d, ax
0x18008e92a  or      r9d, 80070000h
0x18008e931  mov     [rsp+520h+var_4F0], r9d
0x18008e936  test    r9d, r9d
0x18008e939  js      loc_18008EA12
0x18008e93f  xor     edx, edx; Val
0x18008e941  mov     r8d, 176h; Size
0x18008e947  lea     rcx, [rbp+420h+var_3E0]; void *
0x18008e94b  call    memset_0
0x18008e950  mov     [rsp+520h+var_4D8], 0BBh
0x18008e958  mov     [rsp+520h+var_500], r12; PFILETIME
0x18008e95d  lea     r9, [rsp+520h+var_4D8]; unsigned int *
0x18008e962  lea     r8, [rbp+420h+var_3E0]; unsigned __int16 *
0x18008e966  mov     edx, edi; unsigned int
0x18008e968  lea     rcx, [rbp+420h+var_4A0]; this
0x18008e96c  call    ?EnumKey@CRegKey@ATL@@QEAAJKPEAGPEAKPEAU_FILETIME@@@Z; ATL::CRegKey::EnumKey(ulong,ushort *,ulong *,_FILETIME *)
0x18008e971  mov     r9d, eax
0x18008e974  cmp     eax, 103h
0x18008e979  jz      short loc_18008E9BD
0x18008e97b  test    eax, eax
0x18008e97d  jle     short loc_18008E98A
0x18008e97f  movzx   r9d, ax
0x18008e983  or      r9d, 80070000h
0x18008e98a  mov     [rsp+520h+var_4F0], r9d
0x18008e98f  test    r9d, r9d
0x18008e992  js      short loc_18008E9D5
0x18008e994  lea     rdx, [rbp+420h+var_3E0]
0x18008e998  mov     rcx, rsi
0x18008e99b  call    cs:__imp__o__wcsicmp
0x18008e9a1  test    eax, eax
0x18008e9a3  jz      short loc_18008E9A9
0x18008e9a5  inc     edi
0x18008e9a7  jmp     short loc_18008E93F
0x18008e9a9  lea     rdx, [rsp+520h+var_4E8]
0x18008e9ae  lea     rcx, [rsp+520h+var_4D0]
0x18008e9b3  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18008e9b8  mov     rbx, [rsp+520h+var_4D0]
0x18008e9bd  cmp     [rbx-10h], r12d
0x18008e9c1  jnz     short loc_18008E9DD
0x18008e9c3  inc     r14d
0x18008e9c6  lea     rcx, [rsp+520h+var_4E8]
0x18008e9cb  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008e9d0  jmp     loc_18008E85E
0x18008e9d5  mov     r8d, 313Eh
0x18008e9db  jmp     short loc_18008EA23
0x18008e9dd  mov     [rsp+520h+var_4F8], rsi
0x18008e9e2  mov     [rsp+520h+var_500], rbx
0x18008e9e7  lea     r9, aFoundAccountLs; "Found Account %ls for SID %ls."
0x18008e9ee  mov     r8d, 314Ah; unsigned int
0x18008e9f4  mov     rdx, r13; char *
0x18008e9f7  mov     r14d, 5
0x18008e9fd  mov     ecx, r14d; unsigned __int8
0x18008ea00  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008ea05  nop
0x18008ea06  lea     rcx, [rsp+520h+var_4E8]
0x18008ea0b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008ea10  jmp     short loc_18008EA54
0x18008ea12  mov     r8d, 3129h
0x18008ea18  jmp     short loc_18008EA23
0x18008ea1a  mov     r9d, edi; int
0x18008ea1d  mov     r8d, 311Ch; unsigned int
0x18008ea23  lea     rax, aHrHresultFromW_9; "hr = HRESULT_FROM_WIN32(regOpsStatus)"
0x18008ea2a  mov     [rsp+520h+var_500], rax; char *
0x18008ea2f  lea     rdx, aCleanupsystems; "CleanupSystemStoreEntryForSid"
0x18008ea36  mov     rcx, r13; char *
0x18008ea39  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18008ea3e  nop
0x18008ea3f  lea     rcx, [rsp+520h+var_4E8]
0x18008ea44  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18008ea49  jmp     loc_18008ECB9
0x18008ea4e  mov     r14d, 5
0x18008ea54  cmp     [rbx-10h], r12d
0x18008ea58  jnz     short loc_18008EA7F
0x18008ea5a  mov     [rsp+520h+var_500], rsi
0x18008ea5f  lea     r9, aSidLsNotFoundI; "SID %ls not found in system store."
0x18008ea66  mov     r8d, 3152h; unsigned int
0x18008ea6c  mov     rdx, r13; char *
0x18008ea6f  mov     ecx, r14d; unsigned __int8
0x18008ea72  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18008ea77  mov     [rsp+520h+var_4F0], 525h
0x18008ea7f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008ea86  mov     ecx, 120h; unsigned __int64
0x18008ea8b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008ea90  mov     rdi, rax
0x18008ea93  mov     qword ptr [rsp+520h+var_4E0], rax
0x18008ea98  test    rax, rax
0x18008ea9b  jz      short loc_18008EAE3
0x18008ea9d  lea     rax, [rsp+520h+var_4E8]
0x18008eaa2  mov     [rbp+420h+var_3F0], rax
0x18008eaa6  mov     rdx, rsi
0x18008eaa9  lea     rcx, [rsp+520h+var_4E8]
0x18008eaae  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18008eab3  mov     rbx, rax
0x18008eab6  lea     rdx, [rsp+520h+var_4D0]
0x18008eabb  lea     rcx, [rsp+520h+var_4D8]
0x18008eac0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18008eac5  nop
0x18008eac6  mov     dword ptr [rsp+520h+var_500], r12d
0x18008eacb  lea     r9, [rsp+520h+var_4B8]
0x18008ead0  mov     r8, rbx
0x18008ead3  mov     rdx, rax
0x18008ead6  mov     rcx, rdi
0x18008ead9  call    ??0CStoredIdentity@@QEAA@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0AEAU_LUID@@H@Z; CStoredIdentity::CStoredIdentity(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,_LUID &,int)
0x18008eade  mov     rbx, rax
0x18008eae1  jmp     short loc_18008EAE6
0x18008eae3  mov     rbx, r12
0x18008eae6  lea     rcx, [rsp+520h+var_4C0]
0x18008eaeb  call    ?Deinit@?$CAutoRefPtr@VIStoredIdentity@@@@IEAAXXZ; CAutoRefPtr<IStoredIdentity>::Deinit(void)
0x18008eaf0  mov     [rsp+520h+var_4C0], rbx
0x18008eaf5  test    rbx, rbx
0x18008eaf8  jnz     short loc_18008EB07
0x18008eafa  mov     [rsp+520h+var_4F0], 8007000Eh
0x18008eb02  jmp     loc_18008ECB9
0x18008eb07  mov     [rsp+520h+var_4D8], r12d
0x18008eb0c  mov     [rsp+520h+var_4E8], rbx
0x18008eb11  lock inc dword ptr [rbx+8]
0x18008eb15  lea     rdx, [rsp+520h+var_4E8]
0x18008eb1a  lea     rcx, [rbp+420h+var_450]
0x18008eb1e  call    ??0CStoredIdentityTransaction@@QEAA@V?$CAutoRefPtr@VCStoredIdentity@@@@@Z; CStoredIdentityTransaction::CStoredIdentityTransaction(CAutoRefPtr<CStoredIdentity>)
0x18008eb23  nop
0x18008eb24  mov     rdi, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18008eb2b  add     rdi, 858h
0x18008eb32  mov     [rsp+520h+var_4A8], rdi
0x18008eb37  mov     dl, 1; Wait
0x18008eb39  mov     rcx, rdi; Resource
0x18008eb3c  call    cs:__imp_RtlAcquireResourceExclusive
  ... truncated ...
```
