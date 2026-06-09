# CClientConfigDataCacheManager::Initialize(IClientConfig *)

- ea: `0x1800c5a90`
- end: `0x1800c5e1c`
- name: `?Initialize@CClientConfigDataCacheManager@@QEAAJPEAVIClientConfig@@@Z`
- size: `908`
- prototype: `__int64 __fastcall(CClientConfigDataCacheManager *__hidden this, struct IClientConfig *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005ceb0`

## callees

- `0x18000c050`
- `0x180013fb4`
- `0x1800151c4`
- `0x180015860`
- `0x180017af0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x180025e24`
- `0x180026c18`
- `0x180048e40`
- `0x180080298`
- `0x180085c7c`
- `0x180086134`
- `0x18008b790`
- `0x1800c4f64`
- `0x1800c5a90`
- `0x1800c5e24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5dc3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c5dc3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c5c25`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800c5c25`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c5b39`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c5b43`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c5b39`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800c5b43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5c2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c5c2f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c5b5a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800c5b5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5b2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c5b2f`

## string_xrefs

- `0x1800c5adf`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\clientconfig.cpp`
- `0x1800c5ab0`: `CClientConfigDataCacheManager::Initialize`
- `0x1800c5bde`: `.devicedns.live.com`
- `0x1800c5c35`: `ServiceEnvironment`
- `0x1800c5ce2`: `hr = InitializePathsAndMutableConfigs()`
- `0x1800c5d1c`: `hr = DownloadAndReloadConfig()`
- `0x1800c5dd4`: `CoCreateInstance(CLSID_NetworkListManager) failed = 0x%x assuming network connectivity`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CClientConfigDataCacheManager::Initialize(
        CClientConfigDataCacheManager *this,
        struct IClientConfig *a2)
{
  _QWORD *v3; // r14
  int v4; // eax
  int Configuration; // eax
  CClientConfigDataCacheManager *v6; // rcx
  int v7; // eax
  int v8; // eax
  HRESULT Instance; // eax
  unsigned int v10; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-30h]
  LPVOID *ppva; // [rsp+20h] [rbp-30h]
  LPVOID *ppvb; // [rsp+20h] [rbp-30h]
  _QWORD v15[4]; // [rsp+30h] [rbp-20h] BYREF
  char *v16; // [rsp+90h] [rbp+40h] BYREF
  int String; // [rsp+98h] [rbp+48h] BYREF
  int v18; // [rsp+9Ch] [rbp+4Ch]
  char v19; // [rsp+A0h] [rbp+50h] BYREF

  v18 = HIDWORD(a2);
  String = 0;
  v15[0] = "CClientConfigDataCacheManager::Initialize";
  v15[1] = &String;
  v15[2] = 0;
  v15[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    "CClientConfigDataCacheManager::Initialize",
    (const char *)0x392,
    0,
    (const unsigned __int16 *)ppv);
  if ( *(_BYTE *)this )
  {
    String = 0;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "CClientConfigDataCacheManager::Initialize",
      0x394u,
      0,
      "!m_bInitialized");
    goto LABEL_20;
  }
  v16 = (char *)this + 832;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 864));
  ResetEvent(*((HANDLE *)this + 107));
  ResetEvent(*((HANDLE *)this + 106));
  _InterlockedIncrement((volatile signed __int32 *)this + 210);
  if ( *((int *)this + 211) > 0 )
    WaitForSingleObject(*((HANDLE *)this + 106), 0xFFFFFFFF);
  *((_QWORD *)this + 103) = &off_1801C23E0;
  *((_DWORD *)this + 100) = 120000;
  *((_DWORD *)this + 101) = 60000;
  *((_DWORD *)this + 102) = 30000;
  *((_DWORD *)this + 103) = 30000;
  *((_DWORD *)this + 106) = 0;
  *((_DWORD *)this + 138) = 900;
  *((_DWORD *)this + 154) = 5;
  *((_DWORD *)this + 155) = 600;
  *((_DWORD *)this + 156) = 60000;
  *((_DWORD *)this + 104) = 3;
  *((_DWORD *)this + 195) = 86400;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (char *)this + 560,
    ".devicedns.live.com");
  *((_BYTE *)this + 120) = 0;
  v3 = (_QWORD *)((char *)this + 280);
  ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 280, L"production");
  ATL::CSimpleStringT<char,0>::SetString((char *)this + 32, "{DF60E2DF-88AD-4526-AE21-83D130EF0F68}");
  CClientConfigDataCacheManager::GenerateUserAgentString(this);
  _InterlockedDecrement((volatile signed __int32 *)this + 210);
  SetEvent(*((HANDLE *)this + 107));
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 864));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v19,
    L"ServiceEnvironment");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    L"Software\\Microsoft\\IdentityCRL");
  String = Reg_QueryString(HKEY_LOCAL_MACHINE, (__int64)this + 280);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v16);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v19);
  if ( String < 0 )
  {
    LODWORD(ppva) = String;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      0x3C2u,
      L"Failed query of environment: 0x%x",
      ppva);
  }
  TracePrintW(
    4u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
    0x3C5u,
    L"Environment: '%ls'. ",
    *v3);
  v4 = CClientConfigDataCacheManager::InitializePathsAndMutableConfigs(this);
  String = v4;
  if ( v4 >= 0 )
  {
    Configuration = CClientConfigDataCacheManager::LoadConfiguration(this);
    String = Configuration;
    if ( *((_BYTE *)this + 1) )
    {
      v7 = CClientConfigDataCacheManager::DownloadAndReloadConfig(this);
      String = v7;
      if ( v7 < 0 )
      {
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          "CClientConfigDataCacheManager::Initialize",
          0x3CFu,
          v7,
          "hr = DownloadAndReloadConfig()");
        goto LABEL_20;
      }
    }
    else if ( Configuration < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        "CClientConfigDataCacheManager::Initialize",
        0x3D3u,
        Configuration,
        "hr");
      goto LABEL_20;
    }
    CClientConfigDataCacheManager::UpdateRegistryWithLoginUrl(v6);
    CClientConfigDataCacheManager::LoadClockSkew(this);
    v8 = CClientConfigDataCacheManager::InitializeDownloadMgr(this);
    String = v8;
    if ( v8 >= 0 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        (char *)this + 24,
        L"%s\\%s",
        L"Software\\Microsoft\\IdentityCRL\\DeviceIdentities",
        *v3);
      Instance = CoCreateInstance(
                   &CLSID_NetworkListManager,
                   0,
                   1u,
                   &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
                   (LPVOID *)this + 119);
      String = Instance;
      if ( Instance < 0 )
      {
        LODWORD(ppvb) = Instance;
        TracePrintW(
          3u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
          0x3E7u,
          L"CoCreateInstance(CLSID_NetworkListManager) failed = 0x%x assuming network connectivity",
          ppvb);
        *((_QWORD *)this + 119) = 0;
        String = 0;
      }
      *(_BYTE *)this = 1;
    }
    else
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
        "CClientConfigDataCacheManager::Initialize",
        0x3DDu,
        v8,
        "hr = InitializeDownloadMgr()");
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\clientconfig.cpp",
      "CClientConfigDataCacheManager::Initialize",
      0x3C7u,
      v4,
      "hr = InitializePathsAndMutableConfigs()");
  }
LABEL_20:
  v10 = String;
  CTraceFuncW<long>::~CTraceFuncW<long>(v15);
  return v10;
}

```

## disassembly

```asm
0x1800c5a90  mov     [rsp-38h+arg_8], rdx
0x1800c5a95  push    rbp
0x1800c5a96  push    rbx
0x1800c5a97  push    rsi
0x1800c5a98  push    rdi
0x1800c5a99  push    r12
0x1800c5a9b  push    r13
0x1800c5a9d  push    r14
0x1800c5a9f  mov     rbp, rsp
0x1800c5aa2  sub     rsp, 50h
0x1800c5aa6  mov     rbx, rcx
0x1800c5aa9  mov     dword ptr [rbp+arg_8], 0
0x1800c5ab0  lea     r13, aCclientconfigd_12; "CClientConfigDataCacheManager::Initiali"...
0x1800c5ab7  mov     [rbp+var_20], r13
0x1800c5abb  lea     rax, [rbp+arg_8]
0x1800c5abf  mov     [rbp+var_18], rax
0x1800c5ac3  mov     [rbp+var_10], 0
0x1800c5acb  mov     [rbp+var_8], 0
0x1800c5ad3  xor     r9d, r9d; unsigned int
0x1800c5ad6  mov     r8d, 392h; char *
0x1800c5adc  mov     rdx, r13; char *
0x1800c5adf  lea     r12, aOnecoreuapDsEx_58; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x1800c5ae6  mov     rcx, r12; this
0x1800c5ae9  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800c5aee  nop
0x1800c5aef  cmp     byte ptr [rbx], 0
0x1800c5af2  jz      short loc_1800C5B20
0x1800c5af4  mov     dword ptr [rbp+arg_8], 0
0x1800c5afb  lea     rax, aMBinitialized; "!m_bInitialized"
0x1800c5b02  mov     [rsp+50h+ppv], rax; char *
0x1800c5b07  xor     r9d, r9d; int
0x1800c5b0a  mov     r8d, 394h; unsigned int
0x1800c5b10  mov     rdx, r13; char *
0x1800c5b13  mov     rcx, r12; char *
0x1800c5b16  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800c5b1b  jmp     loc_1800C5DFF
0x1800c5b20  lea     rdi, [rbx+340h]
0x1800c5b27  mov     [rbp+arg_0], rdi
0x1800c5b2b  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800c5b2f  call    cs:__imp_EnterCriticalSection
0x1800c5b35  mov     rcx, [rdi+18h]; hEvent
0x1800c5b39  call    cs:__imp_ResetEvent
0x1800c5b3f  mov     rcx, [rdi+10h]; hEvent
0x1800c5b43  call    cs:__imp_ResetEvent
0x1800c5b49  lock inc dword ptr [rdi+8]
0x1800c5b4d  cmp     dword ptr [rdi+0Ch], 0
0x1800c5b51  jle     short loc_1800C5B61
0x1800c5b53  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800c5b56  mov     rcx, [rdi+10h]; hHandle
0x1800c5b5a  call    cs:__imp_WaitForSingleObject
0x1800c5b60  nop
0x1800c5b61  lea     rax, off_1801C23E0
0x1800c5b68  mov     [rbx+338h], rax
0x1800c5b6f  mov     dword ptr [rbx+190h], 1D4C0h
0x1800c5b79  mov     ecx, 0EA60h
0x1800c5b7e  mov     [rbx+194h], ecx
0x1800c5b84  mov     eax, 7530h
0x1800c5b89  mov     [rbx+198h], eax
0x1800c5b8f  mov     [rbx+19Ch], eax
0x1800c5b95  mov     dword ptr [rbx+1A8h], 0
0x1800c5b9f  mov     dword ptr [rbx+228h], 384h
0x1800c5ba9  mov     dword ptr [rbx+268h], 5
0x1800c5bb3  mov     dword ptr [rbx+26Ch], 258h
0x1800c5bbd  mov     [rbx+270h], ecx
0x1800c5bc3  mov     dword ptr [rbx+1A0h], 3
0x1800c5bcd  mov     dword ptr [rbx+30Ch], 15180h
0x1800c5bd7  lea     rcx, [rbx+230h]
0x1800c5bde  lea     rdx, aDevicednsLiveC; ".devicedns.live.com"
0x1800c5be5  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x1800c5bea  mov     byte ptr [rbx+78h], 0
0x1800c5bee  lea     r14, [rbx+118h]
0x1800c5bf5  lea     rdx, aProduction; "production"
0x1800c5bfc  mov     rcx, r14
0x1800c5bff  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800c5c04  lea     rcx, [rbx+20h]
0x1800c5c08  lea     rdx, aDf60e2df88ad45; "{DF60E2DF-88AD-4526-AE21-83D130EF0F68}"
0x1800c5c0f  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x1800c5c14  mov     rcx, rbx; this
0x1800c5c17  call    ?GenerateUserAgentString@CClientConfigDataCacheManager@@AEAAJXZ; CClientConfigDataCacheManager::GenerateUserAgentString(void)
0x1800c5c1c  nop
0x1800c5c1d  lock dec dword ptr [rdi+8]
0x1800c5c21  mov     rcx, [rdi+18h]; hEvent
0x1800c5c25  call    cs:__imp_SetEvent
0x1800c5c2b  lea     rcx, [rdi+20h]; lpCriticalSection
0x1800c5c2f  call    cs:__imp_LeaveCriticalSection
0x1800c5c35  lea     rdx, aServiceenviron; "ServiceEnvironment"
0x1800c5c3c  lea     rcx, [rbp+arg_10]
0x1800c5c40  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800c5c45  nop
0x1800c5c46  lea     rdx, SubKey; "Software\\Microsoft\\IdentityCRL"
0x1800c5c4d  lea     rcx, [rbp+arg_0]
0x1800c5c51  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800c5c56  nop
0x1800c5c57  mov     [rsp+50h+ppv], r14; __int64
0x1800c5c5c  mov     esi, 1
0x1800c5c61  mov     r9d, esi
0x1800c5c64  lea     r8, [rbp+arg_10]
0x1800c5c68  lea     rdx, [rbp+arg_0]
0x1800c5c6c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x1800c5c73  call    ?Reg_QueryString@@YAJPEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1KAEAV23@@Z; Reg_QueryString(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800c5c78  mov     dword ptr [rbp+arg_8], eax
0x1800c5c7b  lea     rcx, [rbp+arg_0]
0x1800c5c7f  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c5c84  nop
0x1800c5c85  lea     rcx, [rbp+arg_10]
0x1800c5c89  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x1800c5c8e  mov     eax, dword ptr [rbp+arg_8]
0x1800c5c91  test    eax, eax
0x1800c5c93  jns     short loc_1800C5CB1
0x1800c5c95  mov     dword ptr [rsp+50h+ppv], eax
0x1800c5c99  lea     r9, aFailedQueryOfE; "Failed query of environment: 0x%x"
0x1800c5ca0  mov     r8d, 3C2h; unsigned int
0x1800c5ca6  mov     rdx, r12; char *
0x1800c5ca9  lea     ecx, [rsi+1]; unsigned __int8
0x1800c5cac  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c5cb1  mov     rax, [r14]
0x1800c5cb4  mov     [rsp+50h+ppv], rax
0x1800c5cb9  lea     r9, aEnvironmentLs; "Environment: '%ls'. "
0x1800c5cc0  mov     r8d, 3C5h; unsigned int
0x1800c5cc6  mov     rdx, r12; char *
0x1800c5cc9  mov     ecx, 4; unsigned __int8
0x1800c5cce  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c5cd3  mov     rcx, rbx; this
0x1800c5cd6  call    ?InitializePathsAndMutableConfigs@CClientConfigDataCacheManager@@AEAAJXZ; CClientConfigDataCacheManager::InitializePathsAndMutableConfigs(void)
0x1800c5cdb  mov     dword ptr [rbp+arg_8], eax
0x1800c5cde  test    eax, eax
0x1800c5ce0  jns     short loc_1800C5CFC
0x1800c5ce2  lea     rcx, aHrInitializepa; "hr = InitializePathsAndMutableConfigs()"
0x1800c5ce9  mov     [rsp+50h+ppv], rcx
0x1800c5cee  mov     r9d, eax
0x1800c5cf1  mov     r8d, 3C7h
0x1800c5cf7  jmp     loc_1800C5B10
0x1800c5cfc  mov     rcx, rbx; this
0x1800c5cff  call    ?LoadConfiguration@CClientConfigDataCacheManager@@AEAAJXZ; CClientConfigDataCacheManager::LoadConfiguration(void)
0x1800c5d04  mov     dword ptr [rbp+arg_8], eax
0x1800c5d07  cmp     byte ptr [rbx+1], 0
0x1800c5d0b  jz      short loc_1800C5D36
0x1800c5d0d  mov     rcx, rbx; this
0x1800c5d10  call    ?DownloadAndReloadConfig@CClientConfigDataCacheManager@@QEAAJXZ; CClientConfigDataCacheManager::DownloadAndReloadConfig(void)
0x1800c5d15  mov     dword ptr [rbp+arg_8], eax
0x1800c5d18  test    eax, eax
0x1800c5d1a  jns     short loc_1800C5D54
0x1800c5d1c  lea     rcx, aHrDownloadandr; "hr = DownloadAndReloadConfig()"
0x1800c5d23  mov     [rsp+50h+ppv], rcx
0x1800c5d28  mov     r9d, eax
0x1800c5d2b  mov     r8d, 3CFh
0x1800c5d31  jmp     loc_1800C5B10
0x1800c5d36  test    eax, eax
0x1800c5d38  jns     short loc_1800C5D54
0x1800c5d3a  lea     rcx, aHr; "hr"
0x1800c5d41  mov     [rsp+50h+ppv], rcx
0x1800c5d46  mov     r9d, eax
0x1800c5d49  mov     r8d, 3D3h
0x1800c5d4f  jmp     loc_1800C5B10
0x1800c5d54  call    ?UpdateRegistryWithLoginUrl@CClientConfigDataCacheManager@@QEAAXXZ; CClientConfigDataCacheManager::UpdateRegistryWithLoginUrl(void)
0x1800c5d59  mov     rcx, rbx; this
0x1800c5d5c  call    ?LoadClockSkew@CClientConfigDataCacheManager@@AEAAJXZ; CClientConfigDataCacheManager::LoadClockSkew(void)
0x1800c5d61  mov     rcx, rbx; this
0x1800c5d64  call    ?InitializeDownloadMgr@CClientConfigDataCacheManager@@AEAAJXZ; CClientConfigDataCacheManager::InitializeDownloadMgr(void)
0x1800c5d69  mov     dword ptr [rbp+arg_8], eax
0x1800c5d6c  test    eax, eax
0x1800c5d6e  jns     short loc_1800C5D8A
0x1800c5d70  lea     rcx, aHrInitializedo; "hr = InitializeDownloadMgr()"
0x1800c5d77  mov     [rsp+50h+ppv], rcx
0x1800c5d7c  mov     r9d, eax
0x1800c5d7f  mov     r8d, 3DDh
0x1800c5d85  jmp     loc_1800C5B10
0x1800c5d8a  lea     rcx, [rbx+18h]
0x1800c5d8e  mov     r9, [r14]
0x1800c5d91  lea     r8, aSoftwareMicros_10; "Software\\Microsoft\\IdentityCRL\\Devic"...
0x1800c5d98  lea     rdx, aSS_1; "%s\\%s"
0x1800c5d9f  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800c5da4  lea     rdi, [rbx+3B8h]
0x1800c5dab  mov     [rsp+50h+ppv], rdi; ppv
0x1800c5db0  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x1800c5db7  mov     r8d, esi; dwClsContext
0x1800c5dba  xor     edx, edx; pUnkOuter
0x1800c5dbc  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800c5dc3  call    cs:__imp_CoCreateInstance
0x1800c5dc9  mov     dword ptr [rbp+arg_8], eax
0x1800c5dcc  test    eax, eax
0x1800c5dce  jns     short loc_1800C5DFC
0x1800c5dd0  mov     dword ptr [rsp+50h+ppv], eax
0x1800c5dd4  lea     r9, aCocreateinstan; "CoCreateInstance(CLSID_NetworkListManag"...
0x1800c5ddb  mov     r8d, 3E7h; unsigned int
0x1800c5de1  mov     rdx, r12; char *
0x1800c5de4  mov     ecx, 3; unsigned __int8
0x1800c5de9  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800c5dee  mov     qword ptr [rdi], 0
0x1800c5df5  mov     dword ptr [rbp+arg_8], 0
0x1800c5dfc  mov     [rbx], sil
0x1800c5dff  mov     ebx, dword ptr [rbp+arg_8]
0x1800c5e02  lea     rcx, [rbp+var_20]
0x1800c5e06  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800c5e0b  mov     eax, ebx
0x1800c5e0d  add     rsp, 50h
0x1800c5e11  pop     r14
0x1800c5e13  pop     r13
0x1800c5e15  pop     r12
0x1800c5e17  pop     rdi
0x1800c5e18  pop     rsi
0x1800c5e19  pop     rbx
0x1800c5e1a  pop     rbp
0x1800c5e1b  retn
```
