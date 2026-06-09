# Microsoft::Diagnostics::UserManager::OnGamerAccountChanged(ulong)

- ea: `0x1801c0430`
- end: `0x1801c074b`
- name: `?OnGamerAccountChanged@UserManager@Diagnostics@Microsoft@@AEAAJK@Z`
- size: `795`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UserManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801bebd0`

## callees

- `0x180003a00`
- `0x1800065a4`
- `0x18001cf30`
- `0x18001d160`
- `0x180026ecc`
- `0x180033f3c`
- `0x180034d94`
- `0x18003fd8c`
- `0x18003fe04`
- `0x180040454`
- `0x18004ab70`
- `0x180053218`
- `0x18005d050`
- `0x18007fbe0`
- `0x180080054`
- `0x1800800bc`
- `0x180089d90`
- `0x1800a2284`
- `0x18012de40`
- `0x18015f810`
- `0x180172d70`
- `0x180173510`
- `0x1801bf71c`
- `0x1801c0430`
- `0x1802ae1e4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c0679`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801c0679`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801c0582`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1801c0582`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1801c0460`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x1801c0460`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801c0551`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801c0551`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1801c051f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x1801c051f`

## string_xrefs

- `0x1801c0707`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`
- `0x1801c0739`: `onecore\base\telemetry\utc\service\engine\usermanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Diagnostics::UserManager::OnGamerAccountChanged(
        Microsoft::Diagnostics::UserManager *this,
        unsigned int a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rax
  struct Microsoft::Diagnostics::UserManager::SessionInformation *Session; // rax
  _QWORD *v9; // rbx
  _QWORD *v10; // r15
  CONTEXT *v11; // rsi
  __int64 v12; // r8
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // r8
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  char **v19; // rax
  const char *v20; // r9
  struct Microsoft::Diagnostics::AsimovEventSerializer *AsimovEventSerializer; // rax
  int v23; // [rsp+20h] [rbp-89h]
  HANDLE hToken; // [rsp+48h] [rbp-61h] BYREF
  wchar_t *v25; // [rsp+50h] [rbp-59h] BYREF
  unsigned int v26; // [rsp+58h] [rbp-51h] BYREF
  __int64 v27; // [rsp+60h] [rbp-49h] BYREF
  char **v28; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v29[16]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v30[16]; // [rsp+80h] [rbp-29h] BYREF
  _BYTE v31[16]; // [rsp+90h] [rbp-19h] BYREF
  char *v32[4]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( (unsigned int)XblaIsConsole() )
  {
    if ( (unsigned int)dword_18042D328 > 2 )
    {
      v25 = (wchar_t *)"OnGamerAccountChanged";
      hToken = "!XblaIsConsole()";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)&unk_1803C6BAB,
        v5,
        v6,
        (__int64)&hToken,
        (__int64)&v25);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
    }
  }
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v30, (char *)this + 8);
  Session = Microsoft::Diagnostics::UserManager::GetSession(this, a2);
  v9 = (_QWORD *)*((_QWORD *)Session + 1);
  v10 = (_QWORD *)*((_QWORD *)Session + 2);
  if ( v9 == v10 )
  {
LABEL_22:
    if ( _InterlockedCompareExchange64((_QWORD *)&xmmword_18043BF80 + 1, 0, 0) )
    {
      AsimovEventSerializer = Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::AsimovSharedPartAState::UpdateXblExtensionData((struct Microsoft::Diagnostics::AsimovEventSerializer *)((char *)AsimovEventSerializer + 8));
    }
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v30);
    return 0;
  }
  else
  {
    v11 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
    while ( 1 )
    {
      hToken = 0;
      RtlCaptureContext(v11);
      LOBYTE(v12) = 2;
      Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(v29, 240000, v12, v11);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hToken,
        0);
      v13 = UMgrQueryUserToken(*v9, &hToken);
      v14 = v13;
      if ( v13 < 0 )
        break;
      Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v29);
      if ( (char *)hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL && ImpersonateLoggedOnUser(hToken) )
      {
        std::wstring::wstring(v32);
        v25 = 0;
        if ( (int)XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(&v25) >= 0 )
        {
          v15 = -1;
          do
            ++v15;
          while ( v25[v15] );
          std::wstring::_Assign<wchar_t>(v32, v25, (char *)v15);
        }
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v31, (char *)this + 88);
        std::wstring::operator=(v9 + 5, v32);
        if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 2048) )
        {
          v19 = v32;
          if ( v32[3] > (char *)7 )
            v19 = (char **)v32[0];
          v28 = v19;
          v27 = *v9;
          v26 = a2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(
            v16,
            (unsigned int)&unk_1803C6BE6,
            v17,
            v18,
            (__int64)&v26,
            (__int64)&v27,
            (__int64)&v28);
        }
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v31);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&void wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v32);
        if ( !RevertToSelf() )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x409,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
            v20);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
      v9 += 14;
      if ( v9 == v10 )
        goto LABEL_22;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FE,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\usermanager.cpp",
      (const char *)(unsigned int)v13,
      v23);
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v29);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v30);
    return v14;
  }
}

```

## disassembly

```asm
0x1801c0430  mov     [rsp-8+arg_10], rbx
0x1801c0435  push    rbp
0x1801c0436  push    rsi
0x1801c0437  push    rdi
0x1801c0438  push    r12
0x1801c043a  push    r13
0x1801c043c  push    r14
0x1801c043e  push    r15
0x1801c0440  lea     rbp, [rsp-27h]
0x1801c0445  sub     rsp, 0D0h
0x1801c044c  mov     rax, cs:__security_cookie
0x1801c0453  xor     rax, rsp
0x1801c0456  mov     [rbp+57h+var_40], rax
0x1801c045a  mov     r12d, edx
0x1801c045d  mov     r14, rcx
0x1801c0460  call    cs:__imp_XblaIsConsole
0x1801c0467  nop     dword ptr [rax+rax+00h]
0x1801c046c  xor     r13d, r13d
0x1801c046f  test    eax, eax
0x1801c0471  jz      short loc_1801C04D6
0x1801c0473  mov     eax, cs:dword_18042D328
0x1801c0479  cmp     eax, 2
0x1801c047c  jbe     short loc_1801C04B2
0x1801c047e  lea     rax, aOngameraccount; "OnGamerAccountChanged"
0x1801c0485  mov     [rbp+57h+var_B0], rax
0x1801c0489  lea     rax, aXblaisconsole_0; "!XblaIsConsole()"
0x1801c0490  mov     [rbp+57h+hToken], rax
0x1801c0494  lea     rax, [rbp+57h+var_B0]
0x1801c0498  mov     [rsp+100h+var_D8], rax
0x1801c049d  lea     rax, [rbp+57h+hToken]
0x1801c04a1  mov     qword ptr [rsp+100h+var_E0], rax; int
0x1801c04a6  lea     rdx, unk_1803C6BAB
0x1801c04ad  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801c04b2  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801c04b9  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x1801c04be  test    al, al
0x1801c04c0  jz      short loc_1801C04D6
0x1801c04c2  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801c04c9  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x1801c04ce  mov     rcx, rax; this
0x1801c04d1  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1801c04d6  lea     rdx, [r14+8]
0x1801c04da  lea     rcx, [rbp+57h+var_80]
0x1801c04de  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801c04e3  nop
0x1801c04e4  mov     edx, r12d; unsigned int
0x1801c04e7  mov     rcx, r14; this
0x1801c04ea  call    ?GetSession@UserManager@Diagnostics@Microsoft@@AEAAAEAUSessionInformation@123@K@Z; Microsoft::Diagnostics::UserManager::GetSession(ulong)
0x1801c04ef  mov     rbx, [rax+8]
0x1801c04f3  mov     r15, [rax+10h]
0x1801c04f7  cmp     rbx, r15
0x1801c04fa  jz      loc_1801C06A7
0x1801c0500  mov     ecx, cs:_tls_index
0x1801c0506  mov     rax, gs:58h
0x1801c050f  mov     esi, 40h ; '@'
0x1801c0514  add     rsi, [rax+rcx*8]
0x1801c0518  mov     [rbp+57h+hToken], r13
0x1801c051c  mov     rcx, rsi; ContextRecord
0x1801c051f  call    cs:__imp_RtlCaptureContext
0x1801c0526  nop     dword ptr [rax+rax+00h]
0x1801c052b  mov     r9, rsi
0x1801c052e  mov     r8b, 2
0x1801c0531  mov     edx, 3A980h
0x1801c0536  lea     rcx, [rbp+57h+var_90]
0x1801c053a  call    ??0ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@KVExternalHangBucket@EnumDetails@23@AEBU_CONTEXT@@@Z; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(ulong,Microsoft::Diagnostics::EnumDetails::ExternalHangBucket,_CONTEXT const &)
0x1801c053f  xor     edx, edx
0x1801c0541  lea     rcx, [rbp+57h+hToken]
0x1801c0545  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1801c054a  lea     rdx, [rbp+57h+hToken]
0x1801c054e  mov     rcx, [rbx]
0x1801c0551  call    cs:__imp_UMgrQueryUserToken
0x1801c0558  nop     dword ptr [rax+rax+00h]
0x1801c055d  mov     edi, eax
0x1801c055f  test    eax, eax
0x1801c0561  js      loc_1801C0700
0x1801c0567  lea     rcx, [rbp+57h+var_90]; this
0x1801c056b  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x1801c0570  mov     rcx, [rbp+57h+hToken]; hToken
0x1801c0574  lea     rax, [rcx-1]
0x1801c0578  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801c057c  ja      loc_1801C0691
0x1801c0582  call    cs:__imp_ImpersonateLoggedOnUser
0x1801c0589  nop     dword ptr [rax+rax+00h]
0x1801c058e  test    eax, eax
0x1801c0590  jz      loc_1801C0691
0x1801c0596  mov     [rbp+57h+var_BF], 1
0x1801c059a  lea     rdx, Src
0x1801c05a1  lea     rcx, [rbp+57h+var_60]
0x1801c05a5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801c05aa  nop
0x1801c05ab  mov     [rbp+57h+var_B0], r13
0x1801c05af  lea     rcx, [rbp+57h+var_B0]; wchar_t **
0x1801c05b3  call    ?GetGamerAccountXuidForImpersonatedUser@XblAuthConfig@@SAJPEAPEA_W@Z; XblAuthConfig::GetGamerAccountXuidForImpersonatedUser(wchar_t * *)
0x1801c05b8  test    eax, eax
0x1801c05ba  js      short loc_1801C05D7
0x1801c05bc  mov     rdx, [rbp+57h+var_B0]
0x1801c05c0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801c05c4  inc     r8
0x1801c05c7  cmp     [rdx+r8*2], r13w
0x1801c05cc  jnz     short loc_1801C05C4
0x1801c05ce  lea     rcx, [rbp+57h+var_60]
0x1801c05d2  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1801c05d7  lea     rdx, [r14+58h]
0x1801c05db  lea     rcx, [rbp+57h+var_70]
0x1801c05df  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801c05e4  nop
0x1801c05e5  lea     rcx, [rbx+28h]
0x1801c05e9  lea     rdx, [rbp+57h+var_60]
0x1801c05ed  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801c05f2  mov     eax, cs:dword_18042D328
0x1801c05f8  cmp     eax, 4
0x1801c05fb  jbe     short loc_1801C0657
0x1801c05fd  mov     edx, 800h
0x1801c0602  lea     rcx, dword_18042D328
0x1801c0609  call    _tlgKeywordOn
0x1801c060e  test    al, al
0x1801c0610  jz      short loc_1801C0657
0x1801c0612  lea     rax, [rbp+57h+var_60]
0x1801c0616  cmp     [rbp+57h+var_48], 7
0x1801c061b  cmova   rax, [rbp+57h+var_60]
0x1801c0620  mov     [rbp+57h+var_98], rax
0x1801c0624  mov     rax, [rbx]
0x1801c0627  mov     [rbp+57h+var_A0], rax
0x1801c062b  mov     [rbp+57h+var_A8], r12d
0x1801c062f  lea     rax, [rbp+57h+var_98]
0x1801c0633  mov     [rsp+100h+var_D0], rax
0x1801c0638  lea     rax, [rbp+57h+var_A0]
0x1801c063c  mov     [rsp+100h+var_D8], rax
0x1801c0641  lea     rax, [rbp+57h+var_A8]
0x1801c0645  mov     qword ptr [rsp+100h+var_E0], rax
0x1801c064a  lea     rdx, unk_1803C6BE6
0x1801c0651  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &)
0x1801c0656  nop
0x1801c0657  lea     rcx, [rbp+57h+var_70]
0x1801c065b  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801c0660  nop
0x1801c0661  lea     rcx, [rbp+57h+var_B0]
0x1801c0665  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXPEAX@Z$1?CloseHeapPointer@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void *),&wilp::CloseHeapPointer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801c066a  nop
0x1801c066b  lea     rcx, [rbp+57h+var_60]; this
0x1801c066f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801c0674  nop
0x1801c0675  mov     [rbp+57h+var_BF], r13b
0x1801c0679  call    cs:__imp_RevertToSelf
0x1801c0680  nop     dword ptr [rax+rax+00h]
0x1801c0685  mov     rcx, [rbp+5Fh]; this
0x1801c0689  test    eax, eax
0x1801c068b  jz      loc_1801C0739
0x1801c0691  lea     rcx, [rbp+57h+hToken]
0x1801c0695  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c069a  add     rbx, 70h ; 'p'
0x1801c069e  cmp     rbx, r15
0x1801c06a1  jnz     loc_1801C0518
0x1801c06a7  mov     rdx, r13
0x1801c06aa  xor     eax, eax
0x1801c06ac  lock cmpxchg qword ptr cs:xmmword_18043BF80+8, rdx
0x1801c06b5  jz      short loc_1801C06CD
0x1801c06b7  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801c06be  call    ?GetAsimovEventSerializer@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAsimovEventSerializer@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer(void)
0x1801c06c3  lea     rcx, [rax+8]; this
0x1801c06c7  call    ?UpdateXblExtensionData@AsimovSharedPartAState@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::AsimovSharedPartAState::UpdateXblExtensionData(void)
0x1801c06cc  nop
0x1801c06cd  lea     rcx, [rbp+57h+var_80]
0x1801c06d1  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801c06d6  xor     eax, eax
0x1801c06d8  mov     rcx, [rbp+57h+var_40]
0x1801c06dc  xor     rcx, rsp; StackCookie
0x1801c06df  call    __security_check_cookie
0x1801c06e4  mov     rbx, [rsp+100h+arg_10]
0x1801c06ec  add     rsp, 0D0h
0x1801c06f3  pop     r15
0x1801c06f5  pop     r14
0x1801c06f7  pop     r13
0x1801c06f9  pop     r12
0x1801c06fb  pop     rdi
0x1801c06fc  pop     rsi
0x1801c06fd  pop     rbp
0x1801c06fe  retn
0x1801c0700  mov     rcx, [rbp+5Fh]; this
0x1801c0704  mov     r9d, edi; char *
0x1801c0707  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1801c070e  mov     edx, 3FEh; void *
0x1801c0713  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c0718  lea     rcx, [rbp+57h+var_90]; this
0x1801c071c  call    ??1ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor(void)
0x1801c0721  nop
0x1801c0722  lea     rcx, [rbp+57h+hToken]
0x1801c0726  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c072b  nop
0x1801c072c  lea     rcx, [rbp+57h+var_80]
0x1801c0730  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801c0735  mov     eax, edi
0x1801c0737  jmp     short loc_1801C06D8
0x1801c0739  lea     r8, aOnecoreBaseTel_121; "onecore\\base\\telemetry\\utc\\service"...
0x1801c0740  mov     edx, 409h; void *
0x1801c0745  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
