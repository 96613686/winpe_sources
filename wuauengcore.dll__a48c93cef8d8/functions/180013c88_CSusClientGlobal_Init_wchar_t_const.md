# CSusClientGlobal::Init(wchar_t const *)

- ea: `0x180013c88`
- end: `0x18001429a`
- name: `?Init@CSusClientGlobal@@AEAAJPEB_W@Z`
- size: `1554`
- prototype: `__int64 __fastcall(CSusClientGlobal *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010918`

## callees

- `0x18000def4`
- `0x180013c88`
- `0x180016ce8`
- `0x18003baf4`
- `0x180054a9c`
- `0x18005606c`
- `0x18005a840`
- `0x18005b8a4`
- `0x180103d80`
- `0x1801048f4`
- `0x1801133c8`
- `0x180113cf4`
- `0x180116ae0`
- `0x180117ba0`
- `0x18012b618`
- `0x18012e74c`
- `0x180131a30`
- `0x18013e19c`
- `0x180238960`
- `0x180239110`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013fbf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013fbf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014008`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013e54`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013dc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013e34`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013dc5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013e34`

## string_xrefs

- `0x18001422d`: `Failed to initialize from component %ws`
- `0x180013cee`: `Security checker`
- `0x180013cf9`: `Settings cache`
- `0x180013d04`: `Base directory setup`
- `0x180013d3b`: `Service Manager`
- `0x180013d51`: `Agent`
- `0x180014208`: `C:\__w\1\s\src\Client\Engine\Agent\susclientglobal.cpp`
- `0x180013f54`: `Base directory: %ws`
- `0x180014184`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSusClientGlobal::Init(CSusClientGlobal *this, const wchar_t *a2, __int64 a3, wchar_t **a4)
{
  CDelayedInitTimeoutEvent *inited; // rbx
  signed int v6; // edi
  const WCHAR *RegKeyPath; // rax
  LSTATUS v8; // eax
  void (*v9)(void); // rax
  signed int SusBaseDirectoryW; // edi
  __int64 v11; // rdx
  unsigned int *v12; // r9
  struct ISusDatastore *v13; // r15
  __int64 v14; // rcx
  char *v15; // r12
  int NetworkState; // esi
  int v17; // eax
  const wchar_t *v18; // rcx
  CAgentServiceManager *v19; // rax
  CAgentServiceManager *v20; // rax
  int v21; // eax
  CDelayedInitTimeoutEvent *v22; // rax
  int dwOptions; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-88h] BYREF
  int v27; // [rsp+88h] [rbp-80h]
  _QWORD v28[12]; // [rsp+98h] [rbp-70h]
  wchar_t v29[264]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+340h] [rbp+238h]

  inited = 0;
  v27 = 0;
  memset(v29, 0, 520);
  v28[0] = L"Idle timer";
  v28[1] = L"Security checker";
  v28[2] = L"Settings cache";
  v28[3] = L"Base directory setup";
  v28[4] = L"Data store";
  v28[5] = L"PersistentTimeoutScheduler";
  v28[6] = L"Event subsystem";
  v28[7] = L"Network Cost Manager";
  v28[8] = L"Service Manager";
  v28[9] = L"Reporter";
  v28[10] = L"Agent";
  v6 = 0;
  hKey = 0;
  phkResult = 0;
  *((_DWORD *)this + 2605) = 0;
  RegKeyPath = (const WCHAR *)GetRegKeyPath(13, (__int64)a2, a3, a4);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, RegKeyPath, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v8 )
  {
    v6 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v6 = v8;
  }
  else if ( (int)RegKeyExists(hKey, L"RebootWatch") < 0 )
  {
    *((_DWORD *)this + 2605) = 1;
    RegCreateKeyExW(hKey, L"RebootWatch", 0, 0, 1u, 0x20006u, 0, &phkResult, 0);
  }
  else
  {
    *((_DWORD *)this + 2605) = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v6 < 0 )
    *((_DWORD *)this + 2605) = 0;
  GetSusFileVersionFromSelf();
  WUTrace(0, 0, 1, 4, 0, L"WU client version %hd.%hd.%hd.%hd");
  v9 = (void (*)(void))*((_QWORD *)this + 1247);
  if ( v9 )
    v9();
  SusBaseDirectoryW = CIdleTimer::Init(
                        (CSusClientGlobal *)((char *)this + 9992),
                        (struct ISusReporter *)(((unsigned __int64)this + 2416)
                                              & ((unsigned __int128)-(__int128)((unsigned __int64)this + 2408) >> 64)),
                        (CSusClientGlobal *)((char *)this + 2296));
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 80;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\susclientglobal.cpp",
      (const char *)(unsigned int)SusBaseDirectoryW,
      dwOptions);
    goto LABEL_56;
  }
  ++v27;
  SusBaseDirectoryW = CSusSecurityChecker::Init(this);
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 83;
    goto LABEL_54;
  }
  v27 += 2;
  SusBaseDirectoryW = GetSusBaseDirectoryW(v29, 0x104u, 0, v12);
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 94;
    goto LABEL_54;
  }
  WUTrace(0, 0, 1, 4, 0, L"Base directory: %ws");
  ++v27;
  SusBaseDirectoryW = (*(__int64 (__fastcall **)(char *, __int64, _QWORD))(*((_QWORD *)this + 175) + 8LL))(
                        (char *)this + 1400,
                        1,
                        0);
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 99;
    goto LABEL_54;
  }
  ++v27;
  v13 = (struct ISusDatastore *)(((unsigned __int64)this + 1408)
                               & -(__int64)((CSusClientGlobal *)((char *)this + 1400) != 0));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2312));
  if ( !*((_DWORD *)this + 588) )
  {
    (*(void (__fastcall **)(struct ISusDatastore *))(*(_QWORD *)v13 + 8LL))(v13);
    v14 = *((_QWORD *)this + 295);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 295) = v13;
    *((_DWORD *)this + 588) = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2312));
  ++v27;
  v15 = (char *)this + 216;
  SusBaseDirectoryW = CSusEventSystem::Init(
                        (CSusClientGlobal *)((char *)this + 216),
                        this,
                        (CSusClientGlobal *)((char *)this + 9792));
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 105;
    goto LABEL_54;
  }
  NetworkState = CIpAddressMonitor::GetNetworkState((char *)this + 1216);
  v17 = CIpAddressMonitor::GetNetworkState((char *)this + 1128);
  if ( NetworkState > v17 )
    v17 = NetworkState;
  v18 = L"Connected";
  if ( v17 != 2 )
    v18 = L"Disconnected";
  WUTrace(0, 0, 2048, 4, 0, L"Network state: %ws", v18);
  *((_DWORD *)this + 2626) = 0;
  *((_QWORD *)this + 1322) = v15;
  *((_BYTE *)this + 10512) = 1;
  *((_DWORD *)this + 2610) = 1;
  v27 += 2;
  v19 = (CAgentServiceManager *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
  phkResult = (HKEY)v19;
  if ( v19 )
    v20 = CAgentServiceManager::CAgentServiceManager(v19);
  else
    v20 = 0;
  *((_QWORD *)this + 1303) = v20;
  if ( !v20 )
  {
    SusBaseDirectoryW = -2147024882;
    v11 = 116;
    goto LABEL_54;
  }
  SusBaseDirectoryW = CAgentServiceManager::Init(v20, this, v13);
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 117;
    goto LABEL_54;
  }
  ++v27;
  SusBaseDirectoryW = CReporter::Init((CSusClientGlobal *)((char *)this + 2408), this, v13);
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 120;
    goto LABEL_54;
  }
  ++v27;
  SusBaseDirectoryW = CSusAgent::Init((CSusClientGlobal *)((char *)this + 4184), this, v13);
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 123;
    goto LABEL_54;
  }
  v21 = CWuaClassFactoryBase::RegisterClassFactory((CSusClientGlobal *)((char *)this + 4232));
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5FA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)(unsigned int)v21,
      dwOptions);
  ++v27;
  v22 = (CDelayedInitTimeoutEvent *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v22 )
    inited = CDelayedInitTimeoutEvent::CDelayedInitTimeoutEvent(v22);
  else
    inited = 0;
  SusBaseDirectoryW = inited == 0 ? 0x8007000E : 0;
  if ( !inited )
  {
    v11 = 132;
    goto LABEL_54;
  }
  SusBaseDirectoryW = (*(__int64 (__fastcall **)(char *, CDelayedInitTimeoutEvent *))(*(_QWORD *)v15 + 24LL))(
                        (char *)this + 216,
                        inited);
  if ( SusBaseDirectoryW < 0 )
  {
    v11 = 134;
    goto LABEL_54;
  }
  inited = 0;
  SusBaseDirectoryW = 0;
LABEL_56:
  if ( v27 != 11 )
    WUTrace(0, 0, 1, 1, 0, L"Failed to initialize from component %ws", v28[v27]);
  if ( inited )
    (**(void (__fastcall ***)(CDelayedInitTimeoutEvent *, __int64))inited)(inited, 1);
  return (unsigned int)SusBaseDirectoryW;
}

```

## disassembly

```asm
0x180013c88  mov     rax, rsp
0x180013c8b  mov     [rax+10h], rbx
0x180013c8f  mov     [rax+18h], rsi
0x180013c93  mov     [rax+20h], rdi
0x180013c97  push    rbp
0x180013c98  push    r12
0x180013c9a  push    r13
0x180013c9c  push    r14
0x180013c9e  push    r15
0x180013ca0  lea     rbp, [rax-238h]
0x180013ca7  sub     rsp, 310h
0x180013cae  mov     rax, cs:__security_cookie
0x180013cb5  xor     rax, rsp
0x180013cb8  mov     [rbp+230h+var_30], rax
0x180013cbf  mov     r14, rcx
0x180013cc2  xor     esi, esi
0x180013cc4  mov     ebx, esi
0x180013cc6  mov     [rsp+330h+var_2E0], rbx
0x180013ccb  mov     [rbp+230h+var_2B0], esi
0x180013cce  mov     [rbp+230h+var_240], si
0x180013cd2  xor     edx, edx; Val
0x180013cd4  mov     r8d, 206h; Size
0x180013cda  lea     rcx, [rbp+230h+var_23E]; void *
0x180013cde  call    memset
0x180013ce3  lea     rax, aIdleTimer; "Idle timer"
0x180013cea  mov     [rbp+230h+var_2A0], rax
0x180013cee  lea     rax, aSecurityChecke; "Security checker"
0x180013cf5  mov     [rbp+230h+var_298], rax
0x180013cf9  lea     rax, aSettingsCache; "Settings cache"
0x180013d00  mov     [rbp+230h+var_290], rax
0x180013d04  lea     rax, aBaseDirectoryS; "Base directory setup"
0x180013d0b  mov     [rbp+230h+var_288], rax
0x180013d0f  lea     rax, aDataStore; "Data store"
0x180013d16  mov     [rbp+230h+var_280], rax
0x180013d1a  lea     rax, aPersistenttime; "PersistentTimeoutScheduler"
0x180013d21  mov     [rbp+230h+var_278], rax
0x180013d25  lea     rax, aEventSubsystem; "Event subsystem"
0x180013d2c  mov     [rbp+230h+var_270], rax
0x180013d30  lea     rax, aNetworkCostMan_0; "Network Cost Manager"
0x180013d37  mov     [rbp+230h+var_268], rax
0x180013d3b  lea     rax, aServiceManager; "Service Manager"
0x180013d42  mov     [rbp+230h+var_260], rax
0x180013d46  lea     rax, aReporter; "Reporter"
0x180013d4d  mov     [rbp+230h+var_258], rax
0x180013d51  lea     rax, aAgent; "Agent"
0x180013d58  mov     [rbp+230h+var_250], rax
0x180013d5c  lea     rax, [rbp+230h+var_2B0]
0x180013d60  mov     [rsp+330h+var_2D8], rax
0x180013d65  lea     rax, [rbp+230h+var_2A0]
0x180013d69  mov     qword ptr [rsp+330h+var_2D0], rax
0x180013d6e  lea     r12d, [rsi+1]
0x180013d72  mov     byte ptr [rsp+330h+var_2C8], r12b
0x180013d77  mov     edi, esi
0x180013d79  mov     [rsp+330h+hKey], rsi
0x180013d7e  mov     [rsp+330h+var_2B8], rsi
0x180013d83  mov     [r14+28B4h], esi
0x180013d8a  lea     ecx, [rsi+0Dh]
0x180013d8d  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x180013d92  mov     rdx, rax; lpSubKey
0x180013d95  mov     [rsp+330h+lpdwDisposition], rsi; lpdwDisposition
0x180013d9a  lea     rax, [rsp+330h+hKey]
0x180013d9f  mov     [rsp+330h+phkResult], rax; phkResult
0x180013da4  mov     [rsp+330h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180013da9  mov     r15d, 20006h
0x180013daf  mov     [rsp+330h+samDesired], r15d; samDesired
0x180013db4  mov     [rsp+330h+dwOptions], esi; dwOptions
0x180013db8  xor     r9d, r9d; lpClass
0x180013dbb  xor     r8d, r8d; Reserved
0x180013dbe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013dc5  call    cs:__imp_RegCreateKeyExW
0x180013dcb  test    eax, eax
0x180013dcd  jz      short loc_180013DDF
0x180013dcf  movzx   edi, ax
0x180013dd2  or      edi, 80070000h
0x180013dd8  test    eax, eax
0x180013dda  cmovle  edi, eax
0x180013ddd  jmp     short loc_180013E3A
0x180013ddf  lea     rdx, aRebootwatch; "RebootWatch"
0x180013de6  mov     rcx, [rsp+330h+hKey]
0x180013deb  call    ?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z; RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)
0x180013df0  test    eax, eax
0x180013df2  js      short loc_180013DFD
0x180013df4  mov     [r14+28B4h], esi
0x180013dfb  jmp     short loc_180013E3A
0x180013dfd  mov     [r14+28B4h], r12d
0x180013e04  mov     [rsp+330h+lpdwDisposition], rsi; lpdwDisposition
0x180013e09  lea     rax, [rsp+330h+var_2B8]
0x180013e0e  mov     [rsp+330h+phkResult], rax; phkResult
0x180013e13  mov     [rsp+330h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180013e18  mov     [rsp+330h+samDesired], r15d; samDesired
0x180013e1d  mov     [rsp+330h+dwOptions], r12d; dwOptions
0x180013e22  xor     r9d, r9d; lpClass
0x180013e25  xor     r8d, r8d; Reserved
0x180013e28  lea     rdx, aRebootwatch; "RebootWatch"
0x180013e2f  mov     rcx, [rsp+330h+hKey]; hKey
0x180013e34  call    cs:__imp_RegCreateKeyExW
0x180013e3a  mov     rcx, [rsp+330h+hKey]; hKey
0x180013e3f  test    rcx, rcx
0x180013e42  jz      short loc_180013E4A
0x180013e44  call    cs:__imp_RegCloseKey
0x180013e4a  mov     rcx, [rsp+330h+var_2B8]; hKey
0x180013e4f  test    rcx, rcx
0x180013e52  jz      short loc_180013E5A
0x180013e54  call    cs:__imp_RegCloseKey
0x180013e5a  test    edi, edi
0x180013e5c  jns     short loc_180013E65
0x180013e5e  mov     [r14+28B4h], esi
0x180013e65  call    ?GetSusFileVersionFromSelf@@YA_KXZ; GetSusFileVersionFromSelf(void)
0x180013e6a  movzx   r9d, ax
0x180013e6e  mov     rcx, rax
0x180013e71  shr     rcx, 10h
0x180013e75  movzx   r8d, cx
0x180013e79  mov     rcx, rax
0x180013e7c  shr     rcx, 20h
0x180013e80  movzx   edx, cx
0x180013e83  shr     rax, 30h
0x180013e87  mov     dword ptr [rsp+330h+var_2E8], r9d
0x180013e8c  mov     dword ptr [rsp+330h+lpdwDisposition], r8d
0x180013e91  mov     dword ptr [rsp+330h+phkResult], edx
0x180013e95  mov     dword ptr [rsp+330h+lpSecurityAttributes], eax
0x180013e99  lea     rax, aWuClientVersio; "WU client version %hd.%hd.%hd.%hd"
0x180013ea0  mov     qword ptr [rsp+330h+samDesired], rax
0x180013ea5  mov     qword ptr [rsp+330h+dwOptions], rsi
0x180013eaa  mov     r15d, 4
0x180013eb0  mov     r9d, r15d
0x180013eb3  mov     r8d, r12d
0x180013eb6  xor     edx, edx
0x180013eb8  xor     ecx, ecx
0x180013eba  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013ebf  mov     rax, [r14+26F8h]
0x180013ec6  test    rax, rax
0x180013ec9  jz      short loc_180013ED0
0x180013ecb  call    _guard_dispatch_icall
0x180013ed0  lea     r13, [r14+968h]
0x180013ed7  lea     r8, [r14+8F8h]; struct ISusPersistentTimeoutScheduler *
0x180013ede  mov     rax, r13
0x180013ee1  lea     rcx, [r13+8]
0x180013ee5  neg     rax
0x180013ee8  sbb     rdx, rdx
0x180013eeb  and     rdx, rcx; struct ISusReporter *
0x180013eee  lea     rcx, [r14+2708h]; this
0x180013ef5  call    ?Init@CIdleTimer@@QEAAJPEAVISusReporter@@PEAVISusPersistentTimeoutScheduler@@@Z; CIdleTimer::Init(ISusReporter *,ISusPersistentTimeoutScheduler *)
0x180013efa  mov     edi, eax
0x180013efc  test    eax, eax
0x180013efe  jns     short loc_180013F0A
0x180013f00  mov     edx, 50h ; 'P'
0x180013f05  jmp     loc_180014134
0x180013f0a  add     [rbp+230h+var_2B0], r12d
0x180013f0e  mov     rcx, r14; this
0x180013f11  call    ?Init@CSusSecurityChecker@@QEAAJXZ; CSusSecurityChecker::Init(void)
0x180013f16  mov     edi, eax
0x180013f18  test    eax, eax
0x180013f1a  jns     short loc_180013F26
0x180013f1c  mov     edx, 53h ; 'S'
0x180013f21  jmp     loc_180014134
0x180013f26  add     [rbp+230h+var_2B0], 2
0x180013f2a  xor     r8d, r8d; wchar_t *
0x180013f2d  mov     edx, 104h; unsigned int
0x180013f32  lea     rcx, [rbp+230h+var_240]; wchar_t *
0x180013f36  call    ?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z; GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)
0x180013f3b  mov     edi, eax
0x180013f3d  test    eax, eax
0x180013f3f  jns     short loc_180013F4B
0x180013f41  mov     edx, 5Eh ; '^'
0x180013f46  jmp     loc_180014134
0x180013f4b  lea     rax, [rbp+230h+var_240]
0x180013f4f  mov     [rsp+330h+lpSecurityAttributes], rax
0x180013f54  lea     rax, aBaseDirectoryW; "Base directory: %ws"
0x180013f5b  mov     qword ptr [rsp+330h+samDesired], rax
0x180013f60  mov     qword ptr [rsp+330h+dwOptions], rsi
0x180013f65  mov     r9d, r15d
0x180013f68  mov     r8d, r12d
0x180013f6b  xor     edx, edx
0x180013f6d  xor     ecx, ecx
0x180013f6f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180013f74  add     [rbp+230h+var_2B0], r12d
0x180013f78  lea     rsi, [r14+578h]
0x180013f7f  mov     rax, [rsi]
0x180013f82  xor     r8d, r8d
0x180013f85  mov     edx, r12d
0x180013f88  mov     rcx, rsi
0x180013f8b  mov     rax, [rax+8]
0x180013f8f  call    _guard_dispatch_icall
0x180013f94  mov     edi, eax
0x180013f96  test    eax, eax
0x180013f98  jns     short loc_180013FA4
0x180013f9a  mov     edx, 63h ; 'c'
0x180013f9f  jmp     loc_180014134
0x180013fa4  add     [rbp+230h+var_2B0], r12d
0x180013fa8  lea     rax, [rsi+8]
0x180013fac  neg     rsi
0x180013faf  sbb     r15, r15
0x180013fb2  and     r15, rax
0x180013fb5  lea     rdi, [r14+908h]
0x180013fbc  mov     rcx, rdi; lpCriticalSection
0x180013fbf  call    cs:__imp_EnterCriticalSection
0x180013fc5  xor     esi, esi
0x180013fc7  cmp     [r14+930h], esi
0x180013fce  jnz     short loc_180014005
0x180013fd0  mov     rax, [r15]
0x180013fd3  mov     rcx, r15
0x180013fd6  mov     rax, [rax+8]
0x180013fda  call    _guard_dispatch_icall
0x180013fdf  mov     rcx, [r14+938h]
0x180013fe6  test    rcx, rcx
0x180013fe9  jz      short loc_180013FF7
0x180013feb  mov     rax, [rcx]
0x180013fee  mov     rax, [rax+10h]
0x180013ff2  call    _guard_dispatch_icall
0x180013ff7  mov     [r14+938h], r15
0x180013ffe  mov     [r14+930h], r12d
0x180014005  mov     rcx, rdi; lpCriticalSection
0x180014008  call    cs:__imp_LeaveCriticalSection
0x18001400e  add     [rbp+230h+var_2B0], r12d
0x180014012  lea     r12, [r14+0D8h]
0x180014019  lea     r8, [r14+2640h]; struct CSusTestHook *
0x180014020  mov     rdx, r14; struct CSusClientGlobal *
0x180014023  mov     rcx, r12; this
0x180014026  call    ?Init@CSusEventSystem@@QEAAJPEAVCSusClientGlobal@@PEAVCSusTestHook@@@Z; CSusEventSystem::Init(CSusClientGlobal *,CSusTestHook *)
0x18001402b  mov     edi, eax
0x18001402d  test    eax, eax
0x18001402f  jns     short loc_18001403B
0x180014031  mov     edx, 69h ; 'i'
0x180014036  jmp     loc_180014134
0x18001403b  lea     rdi, [r14+468h]
0x180014042  lea     rcx, [rdi+58h]
0x180014046  call    ?GetNetworkState@CIpAddressMonitor@@QEAA?AW4_tagNetworkState@@XZ; CIpAddressMonitor::GetNetworkState(void)
0x18001404b  mov     esi, eax
0x18001404d  mov     rcx, rdi
0x180014050  call    ?GetNetworkState@CIpAddressMonitor@@QEAA?AW4_tagNetworkState@@XZ; CIpAddressMonitor::GetNetworkState(void)
0x180014055  cmp     esi, eax
0x180014057  cmovg   eax, esi
0x18001405a  lea     rdx, aDisconnected; "Disconnected"
0x180014061  lea     rcx, aConnected; "Connected"
0x180014068  cmp     eax, 2
0x18001406b  cmovnz  rcx, rdx
0x18001406f  mov     [rsp+330h+lpSecurityAttributes], rcx
0x180014074  lea     rax, aNetworkStateWs; "Network state: %ws"
0x18001407b  mov     qword ptr [rsp+330h+samDesired], rax
0x180014080  xor     esi, esi
0x180014082  mov     qword ptr [rsp+330h+dwOptions], rsi; int
0x180014087  xor     edx, edx
0x180014089  xor     ecx, ecx
0x18001408b  lea     r9d, [rsi+4]
0x18001408f  mov     r8d, 800h
0x180014095  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001409a  mov     [r14+2908h], esi
0x1800140a1  mov     [r14+2950h], r12
0x1800140a8  mov     byte ptr [r14+2910h], 1
0x1800140b0  mov     dword ptr [r14+28C8h], 1
0x1800140bb  add     [rbp+230h+var_2B0], 2
0x1800140bf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800140c6  mov     ecx, 120h; unsigned __int64
0x1800140cb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800140d0  mov     [rsp+330h+var_2B8], rax
0x1800140d5  test    rax, rax
0x1800140d8  jz      short loc_1800140E4
0x1800140da  mov     rcx, rax; this
0x1800140dd  call    ??0CAgentServiceManager@@QEAA@XZ; CAgentServiceManager::CAgentServiceManager(void)
0x1800140e2  jmp     short loc_1800140E7
0x1800140e4  mov     rax, rsi
0x1800140e7  mov     [r14+28B8h], rax
0x1800140ee  test    rax, rax
0x1800140f1  jnz     short loc_1800140FD
0x1800140f3  mov     edi, 8007000Eh
0x1800140f8  lea     edx, [rax+74h]
0x1800140fb  jmp     short loc_180014134
0x1800140fd  mov     r8, r15; struct ISusDatastore *
0x180014100  mov     rdx, r14; struct CSusClientGlobal *
0x180014103  mov     rcx, rax; this
0x180014106  call    ?Init@CAgentServiceManager@@QEAAJPEAVCSusClientGlobal@@PEAUISusDatastore@@@Z; CAgentServiceManager::Init(CSusClientGlobal *,ISusDatastore *)
0x18001410b  mov     edi, eax
0x18001410d  test    eax, eax
0x18001410f  jns     short loc_180014118
0x180014111  mov     edx, 75h ; 'u'
0x180014116  jmp     short loc_180014134
0x180014118  inc     [rbp+230h+var_2B0]
0x18001411b  mov     r8, r15; struct ISusDatastore *
0x18001411e  mov     rdx, r14; struct CSusClientGlobal *
0x180014121  mov     rcx, r13; this
0x180014124  call    ?Init@CReporter@@QEAAJPEAVCSusClientGlobal@@PEAUISusDatastore@@@Z; CReporter::Init(CSusClientGlobal *,ISusDatastore *)
0x180014129  mov     edi, eax
0x18001412b  test    eax, eax
0x18001412d  jns     short loc_18001413F
0x18001412f  mov     edx, 78h ; 'x'
0x180014134  mov     r13d, 1
0x18001413a  jmp     loc_1800141FE
0x18001413f  mov     r13d, 1
0x180014145  add     [rbp+230h+var_2B0], r13d
0x180014149  lea     rsi, [r14+1058h]
0x180014150  mov     r8, r15; struct ISusDatastore *
0x180014153  mov     rdx, r14; struct CSusClientGlobal *
0x180014156  mov     rcx, rsi; this
0x180014159  call    ?Init@CSusAgent@@QEAAJPEAVCSusClientGlobal@@PEAUISusDatastore@@@Z; CSusAgent::Init(CSusClientGlobal *,ISusDatastore *)
0x18001415e  mov     edi, eax
0x180014160  test    eax, eax
0x180014162  jns     short loc_18001416D
0x180014164  lea     edx, [r13+7Ah]
0x180014168  jmp     loc_1800141FE
0x18001416d  lea     rcx, [rsi+30h]; this
  ... truncated ...
```
