# CPassportClientLibrary::Uninitialize(void)

- ea: `0x18004f13c`
- end: `0x18004f654`
- name: `?Uninitialize@CPassportClientLibrary@@QEAAJXZ`
- size: `1304`
- prototype: `__int64 __fastcall(CPassportClientLibrary *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004f0d4`
- `0x18005ceb0`

## callees

- `0x18000c050`
- `0x180015fdc`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x1800332e4`
- `0x180034da8`
- `0x180035920`
- `0x180036304`
- `0x1800363a0`
- `0x180036440`
- `0x1800364dc`
- `0x180039d60`
- `0x18003c814`
- `0x18004f13c`
- `0x18005075c`
- `0x18007cdf8`
- `0x18008716c`
- `0x18008b65c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f506`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004f506`
- `CRYPTSP!CryptDestroyKey` at `0x18004f3a2`
- `CRYPTSP!CryptDestroyKey` at `0x18004f3a2`
- `CRYPTSP!CryptReleaseContext` at `0x18004f47b`
- `CRYPTSP!CryptReleaseContext` at `0x18004f47b`

## string_xrefs

- `0x18004f518`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\deviceidhelpers2.cpp`
- `0x18004f189`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f1c1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f2b0`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f317`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f377`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f430`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f461`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f4e9`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f545`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f5c7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18004f36a`: `Uninitialized configuration manager... 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPassportClientLibrary::Uninitialize(CPassportClientLibrary *this)
{
  int v2; // eax
  int v3; // r9d
  unsigned int v4; // r8d
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  CClientConfigDataCacheManager *v9; // rax
  int v10; // eax
  HCRYPTKEY v11; // rcx
  int Error; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  const char *v16; // r9
  int LastError; // eax
  int v18; // eax
  int v19; // eax
  char *v21; // [rsp+20h] [rbp-D8h]
  char *v22; // [rsp+20h] [rbp-D8h]
  char *v23; // [rsp+20h] [rbp-D8h]
  char *v24; // [rsp+20h] [rbp-D8h]
  char *v25; // [rsp+20h] [rbp-D8h]
  char *v26; // [rsp+20h] [rbp-D8h]
  char *v27; // [rsp+20h] [rbp-D8h]
  char *v28; // [rsp+20h] [rbp-D8h]
  int v29; // [rsp+30h] [rbp-C8h] BYREF
  int v30; // [rsp+34h] [rbp-C4h] BYREF
  int v31; // [rsp+38h] [rbp-C0h] BYREF
  int v32; // [rsp+44h] [rbp-B4h] BYREF
  _QWORD v33[4]; // [rsp+48h] [rbp-B0h] BYREF
  CPassportException *v34; // [rsp+68h] [rbp-90h] BYREF
  ATL::CAtlException *v35; // [rsp+70h] [rbp-88h] BYREF
  CPassportException *v36; // [rsp+78h] [rbp-80h] BYREF
  ATL::CAtlException *v37; // [rsp+80h] [rbp-78h] BYREF
  CPassportException *v38; // [rsp+88h] [rbp-70h] BYREF
  ATL::CAtlException *v39; // [rsp+90h] [rbp-68h] BYREF
  CPassportException *v40; // [rsp+B8h] [rbp-40h] BYREF
  ATL::CAtlException *v41; // [rsp+C0h] [rbp-38h] BYREF
  _BYTE v42[48]; // [rsp+C8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  int v45; // [rsp+108h] [rbp+10h] BYREF
  int v46; // [rsp+110h] [rbp+18h]
  _DWORD *v47; // [rsp+118h] [rbp+20h]

  v45 = 0;
  v33[0] = "CPassportClientLibrary::Uninitialize";
  v33[1] = &v45;
  v33[2] = 0;
  v33[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    "CPassportClientLibrary::Uninitialize",
    (const char *)0x1D2,
    0,
    (const unsigned __int16 *)v21);
  v2 = CPassportClientLibrary::VerifyInitialized(this);
  v45 = v2;
  if ( v2 < 0 )
  {
    v23 = "hr = VerifyInitialized()";
    v3 = v2;
    v4 = 468;
LABEL_3:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
      "CPassportClientLibrary::Uninitialize",
      v4,
      v3,
      v23);
    v5 = v45;
    goto LABEL_52;
  }
  v46 = 0;
  v47 = (_DWORD *)((char *)this + 8);
  v6 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF);
  if ( v6 > 1 )
  {
    v3 = 294981;
    v45 = 294981;
    v23 = "InterlockedDecrement((LONG *)&m_dwInitialized) <= 0";
    v4 = 471;
    goto LABEL_3;
  }
  try
  {
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(
      (__int64)v42,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 496),
      1);
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CAutoRefPtr<CSingleIdentity>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CAutoRefPtr<CSingleIdentity>>>::RemoveAll((char *)this + 680);
    ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::RemoveAll((char *)this + 536);
    ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>>::RemoveAll((char *)this + 608);
    ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<unsigned long,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<unsigned long,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>>::RemoveAll((char *)this + 864);
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)v42);
    v7 = 0;
    v45 = 0;
  }
  catch ( CPassportException *v34 )
  {
    v45 = *((_DWORD *)v34 + 2);
    if ( v45 >= 0 )
      v45 = -2147418113;
    goto LABEL_6;
  }
  catch ( ATL::CAtlException *v35 )
  {
    v45 = *(_DWORD *)v35;
    if ( v45 >= 0 )
      v45 = -2147418113;
    goto LABEL_6;
  }
  catch ( std::bad_alloc )
  {
    v45 = -2147024882;
    v7 = -2147024882;
    goto LABEL_7;
  }
  catch ( long v29 )
  {
    v45 = v29;
    if ( v29 >= 0 )
      v45 = -2147418113;
LABEL_6:
    v7 = v45;
    if ( v45 < 0 )
LABEL_7:
      v46 = v7;
  }
  LODWORD(v22) = v7;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    0x1E3u,
    L"Uninitialized identity store... 0x%x",
    v22);
  try
  {
    v45 = CCertManager::Shutdown((CPassportClientLibrary *)((char *)this + 1376));
  }
  catch ( CPassportException *v36 )
  {
    v45 = *((_DWORD *)v36 + 2);
    if ( v45 >= 0 )
      v45 = -2147418113;
  }
  catch ( ATL::CAtlException *v37 )
  {
    v45 = *(_DWORD *)v37;
    if ( v45 >= 0 )
      v45 = -2147418113;
  }
  catch ( std::bad_alloc )
  {
    v45 = -2147024882;
    goto LABEL_10;
  }
  catch ( long v30 )
  {
    v45 = v30;
    if ( v30 >= 0 )
      v45 = -2147418113;
  }
  if ( v45 < 0 )
  {
LABEL_10:
    v8 = v46;
    if ( v46 >= 0 )
      v8 = v45;
    v46 = v8;
  }
  LODWORD(v24) = v45;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    0x1EFu,
    L"Uninitialized cert manager... 0x%x",
    v24);
  try
  {
    v9 = CClientConfigDataCacheManager::theConfigDataManager();
    v45 = CClientConfigDataCacheManager::Uninitialize(v9);
  }
  catch ( CPassportException *v38 )
  {
    v45 = *((_DWORD *)v38 + 2);
    if ( v45 >= 0 )
      v45 = -2147418113;
  }
  catch ( ATL::CAtlException *v39 )
  {
    v45 = *(_DWORD *)v39;
    if ( v45 >= 0 )
      v45 = -2147418113;
  }
  catch ( std::bad_alloc )
  {
    v45 = -2147024882;
    goto LABEL_15;
  }
  catch ( long v31 )
  {
    v45 = v31;
    if ( v31 >= 0 )
      v45 = -2147418113;
  }
  if ( v45 < 0 )
  {
LABEL_15:
    v10 = v46;
    if ( v46 >= 0 )
      v10 = v45;
    v46 = v10;
  }
  LODWORD(v25) = v45;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    0x1FAu,
    L"Uninitialized configuration manager... 0x%x",
    v25);
  CClientConfigDataCacheManager::FreeTheConfigManager();
  v11 = *((_QWORD *)this + 146);
  if ( v11 )
  {
    if ( CryptDestroyKey(v11) )
    {
      *((_QWORD *)this + 146) = 0;
      Error = 0;
    }
    else
    {
      Error = ATL::AtlHresultFromLastError();
    }
    v45 = Error;
  }
  if ( v45 < 0 )
  {
    v13 = v46;
    if ( v46 >= 0 )
      v13 = v45;
    v46 = v13;
  }
  LODWORD(v26) = v45;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    0x20Au,
    L"Uninitialized random key... 0x%x",
    v26);
  if ( *((_QWORD *)this + 147) )
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
      0x210u,
      L"Uninitializing cryptographic provider...");
    if ( CryptReleaseContext(*((_QWORD *)this + 147), 0) )
    {
      *((_QWORD *)this + 147) = 0;
      v14 = 0;
    }
    else
    {
      v14 = ATL::AtlHresultFromLastError();
    }
    v45 = v14;
  }
  if ( v45 < 0 )
  {
    v15 = v46;
    if ( v46 >= 0 )
      v15 = v45;
    v46 = v15;
  }
  LODWORD(v27) = v45;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    0x219u,
    L"Uninitialized cryptographic provider... 0x%x",
    v27);
  if ( !DeviceIdHelpers::m_hProvisioningMutex || CloseHandle(DeviceIdHelpers::m_hProvisioningMutex) )
  {
    v45 = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xF5,
                  (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\deviceidhelpers2.cpp",
                  v16);
    v45 = LastError;
    if ( LastError < 0 )
    {
      LODWORD(v28) = LastError;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
        0x21Eu,
        L"Unable to close mutex for device provisioning 0x%x.",
        v28);
    }
  }
  try
  {
    v45 = CExternalMemoryManager::Uninitialize((LPCRITICAL_SECTION)((char *)this + 1184));
  }
  catch ( CPassportException *v40 )
  {
    v45 = *((_DWORD *)v40 + 2);
    if ( v45 >= 0 )
      v45 = -2147418113;
  }
  catch ( ATL::CAtlException *v41 )
  {
    v45 = *(_DWORD *)v41;
    if ( v45 >= 0 )
      v45 = -2147418113;
  }
  catch ( std::bad_alloc )
  {
    v45 = -2147024882;
    goto LABEL_42;
  }
  catch ( long v32 )
  {
    v45 = v32;
    if ( v32 >= 0 )
      v45 = -2147418113;
  }
  if ( v45 < 0 )
  {
LABEL_42:
    v18 = v46;
    if ( v46 >= 0 )
      v18 = v45;
    v46 = v18;
  }
  LODWORD(v28) = v45;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    0x22Au,
    L"Uninitialized external memory manager... 0x%x",
    v28);
  *((_DWORD *)this + 324) = -1;
  v5 = v45;
  if ( v45 < 0 )
  {
    v19 = v46;
    if ( v46 >= 0 )
      v19 = v45;
    v46 = v19;
  }
  *v47 = 0;
  if ( v46 < 0 && v5 >= 0 )
  {
    v5 = v46;
    v45 = v46;
  }
LABEL_52:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v33);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004f13c  mov     rax, rsp
0x18004f13f  mov     [rax+8], rcx
0x18004f143  push    rbx
0x18004f144  push    rdi
0x18004f145  sub     rsp, 0E8h
0x18004f14c  mov     rbx, rcx
0x18004f14f  mov     dword ptr [rax+10h], 0
0x18004f156  lea     rdi, aCpassportclien_3; "CPassportClientLibrary::Uninitialize"
0x18004f15d  mov     [rsp+0F8h+var_B0], rdi
0x18004f162  lea     rax, [rax+10h]
0x18004f166  mov     [rsp+0F8h+var_A8], rax
0x18004f16b  mov     [rsp+0F8h+var_A0], 0
0x18004f174  mov     [rsp+0F8h+var_98], 0
0x18004f17d  xor     r9d, r9d; unsigned int
0x18004f180  mov     r8d, 1D2h; char *
0x18004f186  mov     rdx, rdi; char *
0x18004f189  lea     rcx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f190  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18004f195  nop
0x18004f196  mov     rcx, rbx; this
0x18004f199  call    ?VerifyInitialized@CPassportClientLibrary@@QEBAJXZ; CPassportClientLibrary::VerifyInitialized(void)
0x18004f19e  mov     [rsp+0F8h+arg_8], eax
0x18004f1a5  test    eax, eax
0x18004f1a7  jns     short loc_18004F1D9
0x18004f1a9  lea     rcx, aHrVerifyinitia; "hr = VerifyInitialized()"
0x18004f1b0  mov     [rsp+0F8h+var_D8], rcx; char *
0x18004f1b5  mov     r9d, eax; int
0x18004f1b8  mov     r8d, 1D4h; unsigned int
0x18004f1be  mov     rdx, rdi; char *
0x18004f1c1  lea     rcx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f1c8  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18004f1cd  mov     ebx, [rsp+0F8h+arg_8]
0x18004f1d4  jmp     loc_18004F62E
0x18004f1d9  mov     [rsp+0F8h+arg_10], 0
0x18004f1e4  mov     rcx, [rsp+0F8h+arg_0]
0x18004f1ec  add     rcx, 8
0x18004f1f0  mov     [rsp+0F8h+arg_18], rcx
0x18004f1f8  or      eax, 0FFFFFFFFh
0x18004f1fb  lock xadd [rcx], eax
0x18004f1ff  sub     eax, 1
0x18004f202  jle     short loc_18004F226
0x18004f204  mov     r9d, 48045h
0x18004f20a  mov     [rsp+0F8h+arg_8], r9d
0x18004f212  lea     rax, aInterlockeddec; "InterlockedDecrement((LONG *)&m_dwIniti"...
0x18004f219  mov     [rsp+0F8h+var_D8], rax
0x18004f21e  mov     r8d, 1D7h
0x18004f224  jmp     short loc_18004F1BE
0x18004f226  mov     rbx, [rsp+0F8h+arg_0]
0x18004f22e  mov     r8b, 1
0x18004f231  lea     rdx, [rbx+1F0h]
0x18004f238  lea     rcx, [rsp+0F8h+var_30]
0x18004f240  call    ??0?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@AEAVCComAutoCriticalSectionWTry@@_N@Z; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::CComCritSecLockWTry<CComAutoCriticalSectionWTry>(CComAutoCriticalSectionWTry &,bool)
0x18004f245  lea     rcx, [rbx+2A8h]
0x18004f24c  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCSingleIdentity@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCSingleIdentity@@@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoRefPtr<CSingleIdentity>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CAutoRefPtr<CSingleIdentity>>>::RemoveAll(void)
0x18004f251  lea     rcx, [rbx+218h]
0x18004f258  call    ?RemoveAll@?$CAtlMap@PEAXV?$CAutoPtr@VCWLIDContext@@@ATL@@V?$CElementTraits@PEAX@2@V?$CAutoPtrElementTraits@VCWLIDContext@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<void *,ATL::CAutoPtr<CWLIDContext>,ATL::CElementTraits<void *>,ATL::CAutoPtrElementTraits<CWLIDContext>>::RemoveAll(void)
0x18004f25d  lea     rcx, [rbx+260h]
0x18004f264  call    ?RemoveAll@?$CAtlMap@U_LUID@@V?$CAutoPtr@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@ATL@@V?$CElementTraits@U_LUID@@@3@V?$CAutoPtrElementTraits@V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CAutoRefPtr@VCIdentityTokenBag@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@V?$CAutoRefPtr@VCIdentityTokenBag@@@@@2@@ATL@@@3@@ATL@@QEAAXXZ; ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CAutoRefPtr<CIdentityTokenBag>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CAutoRefPtr<CIdentityTokenBag>>>>>::RemoveAll(void)
0x18004f269  lea     rcx, [rbx+360h]
0x18004f270  call    ?RemoveAll@?$CAtlMap@U_LUID@@V?$CAutoPtr@V?$CAtlMap@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@ATL@@V?$CElementTraits@U_LUID@@@3@V?$CAutoPtrElementTraits@V?$CAtlMap@KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@K@2@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@3@@ATL@@QEAAXXZ; ATL::CAtlMap<_LUID,ATL::CAutoPtr<ATL::CAtlMap<ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ulong>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>,ATL::CElementTraits<_LUID>,ATL::CAutoPtrElementTraits<ATL::CAtlMap<ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ulong>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>::RemoveAll(void)
0x18004f275  lea     rcx, [rsp+0F8h+var_30]
0x18004f27d  call    ??1?$CComCritSecLockWTry@VCComAutoCriticalSectionWTry@@@@QEAA@XZ; CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>(void)
0x18004f282  xor     eax, eax
0x18004f284  mov     [rsp+0F8h+arg_8], eax
0x18004f28b  jmp     short loc_18004F29F
0x18004f28d  mov     eax, [rsp+0F8h+arg_8]
0x18004f294  test    eax, eax
0x18004f296  jns     short loc_18004F29F
0x18004f298  mov     [rsp+0F8h+arg_10], eax
0x18004f29f  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18004f2a3  lea     r9, aUninitializedI; "Uninitialized identity store... 0x%x"
0x18004f2aa  mov     r8d, 1E3h; unsigned int
0x18004f2b0  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f2b7  mov     ecx, 5; unsigned __int8
0x18004f2bc  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f2c1  nop
0x18004f2c2  mov     rcx, [rsp+0F8h+arg_0]
0x18004f2ca  add     rcx, 560h; this
0x18004f2d1  call    ?Shutdown@CCertManager@@QEAAJXZ; CCertManager::Shutdown(void)
0x18004f2d6  mov     [rsp+0F8h+arg_8], eax
0x18004f2dd  cmp     [rsp+0F8h+arg_8], 0
0x18004f2e5  jge     short loc_18004F2FF
0x18004f2e7  mov     eax, [rsp+0F8h+arg_10]
0x18004f2ee  test    eax, eax
0x18004f2f0  cmovns  eax, [rsp+0F8h+arg_8]
0x18004f2f8  mov     [rsp+0F8h+arg_10], eax
0x18004f2ff  mov     eax, [rsp+0F8h+arg_8]
0x18004f306  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18004f30a  lea     r9, aUninitializedC; "Uninitialized cert manager... 0x%x"
0x18004f311  mov     r8d, 1EFh; unsigned int
0x18004f317  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f31e  mov     ecx, 5; unsigned __int8
0x18004f323  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f328  nop
0x18004f329  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x18004f32e  mov     rcx, rax; this
0x18004f331  call    ?Uninitialize@CClientConfigDataCacheManager@@QEAAJXZ; CClientConfigDataCacheManager::Uninitialize(void)
0x18004f336  mov     [rsp+0F8h+arg_8], eax
0x18004f33d  cmp     [rsp+0F8h+arg_8], 0
0x18004f345  jge     short loc_18004F35F
0x18004f347  mov     eax, [rsp+0F8h+arg_10]
0x18004f34e  test    eax, eax
0x18004f350  cmovns  eax, [rsp+0F8h+arg_8]
0x18004f358  mov     [rsp+0F8h+arg_10], eax
0x18004f35f  mov     eax, [rsp+0F8h+arg_8]
0x18004f366  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18004f36a  lea     r9, aUninitializedC_0; "Uninitialized configuration manager... "...
0x18004f371  mov     r8d, 1FAh; unsigned int
0x18004f377  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f37e  mov     ecx, 5; unsigned __int8
0x18004f383  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f388  call    ?FreeTheConfigManager@CClientConfigDataCacheManager@@SAXXZ; CClientConfigDataCacheManager::FreeTheConfigManager(void)
0x18004f38d  nop
0x18004f38e  mov     rbx, [rsp+0F8h+arg_0]
0x18004f396  mov     rcx, [rbx+490h]; hKey
0x18004f39d  test    rcx, rcx
0x18004f3a0  jz      short loc_18004F3F6
0x18004f3a2  call    cs:__imp_CryptDestroyKey
0x18004f3a8  test    eax, eax
0x18004f3aa  jnz     short loc_18004F3E2
0x18004f3ac  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004f3b1  jmp     short loc_18004F3EF
0x18004f3b3  jmp     loc_18004F28D
0x18004f3b8  mov     eax, [rsp+0F8h+arg_8]
0x18004f3bf  jmp     loc_18004F298
0x18004f3c4  jmp     loc_18004F2DD
0x18004f3c9  jmp     loc_18004F2DD
0x18004f3ce  jmp     loc_18004F2E7
0x18004f3d3  jmp     loc_18004F33D
0x18004f3d8  jmp     loc_18004F33D
0x18004f3dd  jmp     loc_18004F347
0x18004f3e2  mov     qword ptr [rbx+490h], 0
0x18004f3ed  xor     eax, eax
0x18004f3ef  mov     [rsp+0F8h+arg_8], eax
0x18004f3f6  cmp     [rsp+0F8h+arg_8], 0
0x18004f3fe  jge     short loc_18004F418
0x18004f400  mov     eax, [rsp+0F8h+arg_10]
0x18004f407  test    eax, eax
0x18004f409  cmovns  eax, [rsp+0F8h+arg_8]
0x18004f411  mov     [rsp+0F8h+arg_10], eax
0x18004f418  mov     eax, [rsp+0F8h+arg_8]
0x18004f41f  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18004f423  lea     r9, aUninitializedR; "Uninitialized random key... 0x%x"
0x18004f42a  mov     r8d, 20Ah; unsigned int
0x18004f430  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f437  mov     ecx, 5; unsigned __int8
0x18004f43c  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f441  nop
0x18004f442  mov     rbx, [rsp+0F8h+arg_0]
0x18004f44a  cmp     qword ptr [rbx+498h], 0
0x18004f452  jz      short loc_18004F4AF
0x18004f454  lea     r9, aUninitializing; "Uninitializing cryptographic provider.."...
0x18004f45b  mov     r8d, 210h; unsigned int
0x18004f461  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f468  mov     ecx, 5; unsigned __int8
0x18004f46d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f472  xor     edx, edx; dwFlags
0x18004f474  mov     rcx, [rbx+498h]; hProv
0x18004f47b  call    cs:__imp_CryptReleaseContext
0x18004f481  test    eax, eax
0x18004f483  jnz     short loc_18004F49B
0x18004f485  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004f48a  jmp     short loc_18004F4A8
0x18004f48c  jmp     loc_18004F3F6
0x18004f491  jmp     loc_18004F400
0x18004f496  jmp     loc_18004F3F6
0x18004f49b  mov     qword ptr [rbx+498h], 0
0x18004f4a6  xor     eax, eax
0x18004f4a8  mov     [rsp+0F8h+arg_8], eax
0x18004f4af  cmp     [rsp+0F8h+arg_8], 0
0x18004f4b7  jge     short loc_18004F4D1
0x18004f4b9  mov     eax, [rsp+0F8h+arg_10]
0x18004f4c0  test    eax, eax
0x18004f4c2  cmovns  eax, [rsp+0F8h+arg_8]
0x18004f4ca  mov     [rsp+0F8h+arg_10], eax
0x18004f4d1  mov     eax, [rsp+0F8h+arg_8]
0x18004f4d8  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18004f4dc  lea     r9, aUninitializedC_1; "Uninitialized cryptographic provider..."...
0x18004f4e3  mov     r8d, 219h; unsigned int
0x18004f4e9  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f4f0  mov     ecx, 5; unsigned __int8
0x18004f4f5  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f4fa  mov     rcx, cs:?m_hProvisioningMutex@DeviceIdHelpers@@1PEAXEA; hObject
0x18004f501  test    rcx, rcx
0x18004f504  jz      short loc_18004F567
0x18004f506  call    cs:__imp_CloseHandle
0x18004f50c  test    eax, eax
0x18004f50e  jnz     short loc_18004F567
0x18004f510  mov     rcx, [rsp+0F8h]; this
0x18004f518  lea     r8, aOnecoreuapDsEx_44; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f51f  mov     edx, 0F5h; void *
0x18004f524  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004f529  mov     [rsp+0F8h+arg_8], eax
0x18004f530  test    eax, eax
0x18004f532  jns     short loc_18004F572
0x18004f534  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18004f538  lea     r9, aUnableToCloseM; "Unable to close mutex for device provis"...
0x18004f53f  mov     r8d, 21Eh; unsigned int
0x18004f545  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f54c  mov     ecx, 2; unsigned __int8
0x18004f551  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f556  jmp     short loc_18004F572
0x18004f558  jmp     loc_18004F4AF
0x18004f55d  jmp     loc_18004F4B9
0x18004f562  jmp     loc_18004F4AF
0x18004f567  mov     [rsp+0F8h+arg_8], 0
0x18004f572  mov     rcx, [rsp+0F8h+arg_0]
0x18004f57a  add     rcx, 4A0h; lpCriticalSection
0x18004f581  call    ?Uninitialize@CExternalMemoryManager@@QEAAJXZ; CExternalMemoryManager::Uninitialize(void)
0x18004f586  mov     [rsp+0F8h+arg_8], eax
0x18004f58d  cmp     [rsp+0F8h+arg_8], 0
0x18004f595  jge     short loc_18004F5AF
0x18004f597  mov     eax, [rsp+0F8h+arg_10]
0x18004f59e  test    eax, eax
0x18004f5a0  cmovns  eax, [rsp+0F8h+arg_8]
0x18004f5a8  mov     [rsp+0F8h+arg_10], eax
0x18004f5af  mov     eax, [rsp+0F8h+arg_8]
0x18004f5b6  mov     dword ptr [rsp+0F8h+var_D8], eax
0x18004f5ba  lea     r9, aUninitializedE; "Uninitialized external memory manager.."...
0x18004f5c1  mov     r8d, 22Ah; unsigned int
0x18004f5c7  lea     rdx, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18004f5ce  mov     ecx, 5; unsigned __int8
0x18004f5d3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18004f5d8  mov     rax, [rsp+0F8h+arg_0]
0x18004f5e0  mov     dword ptr [rax+510h], 0FFFFFFFFh
0x18004f5ea  mov     ebx, [rsp+0F8h+arg_8]
0x18004f5f1  test    ebx, ebx
0x18004f5f3  jns     short loc_18004F608
0x18004f5f5  mov     eax, [rsp+0F8h+arg_10]
0x18004f5fc  test    eax, eax
0x18004f5fe  cmovns  eax, ebx
0x18004f601  mov     [rsp+0F8h+arg_10], eax
0x18004f608  mov     rax, [rsp+0F8h+arg_18]
0x18004f610  mov     dword ptr [rax], 0
0x18004f616  mov     eax, [rsp+0F8h+arg_10]
0x18004f61d  test    eax, eax
0x18004f61f  jns     short loc_18004F62E
0x18004f621  test    ebx, ebx
0x18004f623  js      short loc_18004F62E
0x18004f625  mov     ebx, eax
0x18004f627  mov     [rsp+0F8h+arg_8], eax
0x18004f62e  lea     rcx, [rsp+0F8h+var_B0]
0x18004f633  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18004f638  mov     eax, ebx
0x18004f63a  add     rsp, 0E8h
0x18004f641  pop     rdi
0x18004f642  pop     rbx
0x18004f643  retn
0x18004f644  jmp     loc_18004F58D
0x18004f649  jmp     loc_18004F58D
0x18004f64e  jmp     loc_18004F597
```
