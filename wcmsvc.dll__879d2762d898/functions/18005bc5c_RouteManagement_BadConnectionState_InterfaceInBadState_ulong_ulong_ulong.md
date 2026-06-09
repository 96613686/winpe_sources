# RouteManagement::BadConnectionState::InterfaceInBadState(ulong,ulong,ulong)

- ea: `0x18005bc5c`
- end: `0x18005c133`
- name: `?InterfaceInBadState@BadConnectionState@RouteManagement@@QEAAXKKK@Z`
- size: `1239`
- prototype: `void __fastcall(RouteManagement::BadConnectionState *__hidden this, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800590c0`

## callees

- `0x1800137a0`
- `0x180027630`
- `0x180031f44`
- `0x180032e80`
- `0x18003322c`
- `0x180034584`
- `0x18005bc5c`
- `0x18005d678`
- `0x18005d890`
- `0x18007b57c`
- `0x180084f50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bcda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c0ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005bcda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c0ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005be96`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bfb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005be96`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005bfb1`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005bf89`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c050`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005bf89`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18005c050`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005bfe2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005c0a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005bfe2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005c0a5`

## string_xrefs

- `0x18005bd05`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerbadconnectionstate.cpp`
- `0x18005bd2a`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerbadconnectionstate.cpp`
- `0x18005bd68`: `onecoreuap\net\wcm\service\base\routemanager\routemanagerbadconnectionstate.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall RouteManagement::BadConnectionState::InterfaceInBadState(
        RouteManagement::BadConnectionState *this,
        int a2,
        int a3,
        int a4)
{
  char *v8; // rdx
  const char *v9; // r9
  const struct RouteManagement::ConnectionStateTelemetry *v10; // rdx
  int v11; // ecx
  int v12; // r8d
  char v13; // r12
  int v14; // ebx
  int TickCount64; // eax
  PTP_TIMER *v16; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v18; // r9
  struct _TP_TIMER **v19; // rbx
  PTP_TIMER v20; // rax
  struct _TP_TIMER *v21; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+40h] [rbp-98h] BYREF
  const char *v23; // [rsp+48h] [rbp-90h] BYREF
  int v24; // [rsp+50h] [rbp-88h] BYREF
  int v25; // [rsp+54h] [rbp-84h]
  __int128 v26; // [rsp+58h] [rbp-80h]
  int v27; // [rsp+68h] [rbp-70h]
  int v28; // [rsp+6Ch] [rbp-6Ch]
  int v29; // [rsp+70h] [rbp-68h]
  int v30; // [rsp+74h] [rbp-64h]
  int v31; // [rsp+78h] [rbp-60h]
  int v32; // [rsp+7Ch] [rbp-5Ch]
  char v33; // [rsp+80h] [rbp-58h]
  LPCRITICAL_SECTION v34; // [rsp+88h] [rbp-50h] BYREF
  struct _FILETIME pftDueTime; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    v8 = (char *)this + 16;
    if ( _InterlockedCompareExchange(&dword_18013F8B0, 0, 0) )
    {
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, v8);
      RouteManagement::BadConnectionState::HandlePowerStateChange(this);
      if ( !*((_BYTE *)this + 96) )
      {
        *((_DWORD *)this + 14) = 2;
        ++*((_DWORD *)this + 22);
        *((_DWORD *)this + 19) = a2;
        *((_DWORD *)this + 20) = a3;
        *((_DWORD *)this + 21) = a4;
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      return;
    }
    v34 = 0;
    wil::EnterCriticalSection(&v34, v8);
    if ( *((_DWORD *)this + 14) == 2 )
    {
      v13 = 0;
    }
    else
    {
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        lpCriticalSection = (LPCRITICAL_SECTION)this;
        v23 = "BadConnectionState::InterfaceInBadState";
        pftDueTime = (struct _FILETIME)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
          v11,
          (unsigned int)byte_18011B961,
          v12,
          (_DWORD)v9,
          (__int64)&pftDueTime,
          (__int64)&v23,
          (__int64)&lpCriticalSection);
      }
      v13 = 1;
      *((_DWORD *)this + 14) = 2;
      ++*((_DWORD *)this + 22);
    }
    if ( *((_DWORD *)this + 20) != a3 )
    {
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        LODWORD(lpCriticalSection) = a3;
        pftDueTime = (struct _FILETIME)"BadConnectionState::InterfaceInBadState (IPv4)";
        v23 = "onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v11,
          (unsigned int)&dword_18011B99C,
          v12,
          (_DWORD)v9,
          (__int64)&v23,
          (__int64)&pftDueTime,
          (__int64)&lpCriticalSection);
      }
      *((_DWORD *)this + 20) = a3;
    }
    if ( *((_DWORD *)this + 21) != a4 )
    {
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        LODWORD(lpCriticalSection) = a4;
        pftDueTime = (struct _FILETIME)"BadConnectionState::InterfaceInBadState (IPv6)";
        v23 = "onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v11,
          (unsigned int)qword_18011B838,
          v12,
          (_DWORD)v9,
          (__int64)&v23,
          (__int64)&pftDueTime,
          (__int64)&lpCriticalSection);
      }
      *((_DWORD *)this + 21) = a4;
    }
    if ( *((_DWORD *)this + 19) != a2 )
    {
      if ( (unsigned int)dword_18013A120 > 5 )
      {
        LODWORD(lpCriticalSection) = a2;
        pftDueTime = (struct _FILETIME)"BadConnectionState::InterfaceInBadState (aggregate)";
        v23 = "onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v11,
          (unsigned int)&dword_18011B874,
          v12,
          (_DWORD)v9,
          (__int64)&v23,
          (__int64)&pftDueTime,
          (__int64)&lpCriticalSection);
      }
      *((_DWORD *)this + 19) = a2;
      if ( v13 )
        goto LABEL_27;
      v14 = *((_DWORD *)this + 16);
      TickCount64 = GetTickCount64();
      v26 = 0;
      v24 = *((_DWORD *)this + 18);
      v25 = *((_DWORD *)this + 22);
      v26 = *(_OWORD *)this;
      v27 = *((_DWORD *)this + 15);
      v28 = *((_DWORD *)this + 19);
      v29 = *((_DWORD *)this + 20);
      v30 = *((_DWORD *)this + 21);
      v31 = TickCount64 - v14;
      v32 = *((_DWORD *)this + 23);
      v33 = *((_BYTE *)this + 96);
      RouteManagement::TraceUpdateBadState(
        (RouteManagement *)&v24,
        (const struct RouteManagement::ConnectionStateTelemetry *)(unsigned int)(TickCount64 - v14));
    }
    if ( !v13 )
    {
LABEL_28:
      v16 = (PTP_TIMER *)((char *)this + 104);
      if ( !*((_QWORD *)this + 13) )
      {
        ThreadpoolTimer = CreateThreadpoolTimer(RouteManagement::BadConnectionState::BadStateTimerCallback, this, 0);
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          (char *)this + 104,
          ThreadpoolTimer);
        if ( !*v16 )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xE8,
            (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp",
            v18);
        *((_QWORD *)this + 8) = GetTickCount64();
        lpCriticalSection = (LPCRITICAL_SECTION)-20000000LL;
        pftDueTime = (struct _FILETIME)-20000000LL;
        SetThreadpoolTimer(*v16, &pftDueTime, 0, 0);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, &WPP_b117651525d03ae6d39c613c7f962000_Traceguids, 2000);
        }
      }
      if ( *((_DWORD *)this + 15) == 2 )
      {
        v19 = (struct _TP_TIMER **)((char *)this + 112);
        if ( !*((_QWORD *)this + 14) )
        {
          v20 = CreateThreadpoolTimer(RouteManagement::BadConnectionState::BadWifiLocationTimerCallback, this, 0);
          wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
            (char *)this + 112,
            v20);
          v21 = *v19;
          if ( !*v19 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0xF9,
              (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp",
              (const char *)retaddr);
          lpCriticalSection = (LPCRITICAL_SECTION)-3000000000LL;
          pftDueTime = (struct _FILETIME)-3000000000LL;
          SetThreadpoolTimer(v21, &pftDueTime, 0, 0);
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              14,
              &WPP_b117651525d03ae6d39c613c7f962000_Traceguids,
              300000);
          }
        }
      }
      if ( v34 )
        LeaveCriticalSection(v34);
      return;
    }
LABEL_27:
    v26 = 0;
    v24 = *((_DWORD *)this + 18);
    v25 = *((_DWORD *)this + 22);
    v26 = *(_OWORD *)this;
    v27 = *((_DWORD *)this + 15);
    v28 = *((_DWORD *)this + 19);
    v29 = *((_DWORD *)this + 20);
    v30 = *((_DWORD *)this + 21);
    v31 = 0;
    v32 = *((_DWORD *)this + 23);
    v33 = *((_BYTE *)this + 96);
    RouteManagement::TraceStartBadState((RouteManagement *)&v24, v10);
    goto LABEL_28;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\routemanager\\routemanagerbadconnectionstate.cpp",
      v9);
  }
}

```

## disassembly

```asm
0x18005bc5c  push    rbx
0x18005bc5e  push    rsi
0x18005bc5f  push    rdi
0x18005bc60  push    r12
0x18005bc62  push    r14
0x18005bc64  push    r15
0x18005bc66  sub     rsp, 0A8h
0x18005bc6d  mov     rax, cs:__security_cookie
0x18005bc74  xor     rax, rsp
0x18005bc77  mov     [rsp+0D8h+var_40], rax
0x18005bc7f  mov     r14d, r9d
0x18005bc82  mov     ebx, r8d
0x18005bc85  mov     r15d, edx
0x18005bc88  mov     rdi, rcx
0x18005bc8b  xor     ecx, ecx
0x18005bc8d  xor     eax, eax
0x18005bc8f  lock cmpxchg cs:dword_18013F8B0, ecx
0x18005bc97  lea     rdx, [rdi+10h]
0x18005bc9b  jz      short loc_18005BCE6
0x18005bc9d  mov     [rsp+0D8h+lpCriticalSection], rcx
0x18005bca2  lea     rcx, [rsp+0D8h+lpCriticalSection]
0x18005bca7  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18005bcac  nop
0x18005bcad  mov     rcx, rdi; this
0x18005bcb0  call    ?HandlePowerStateChange@BadConnectionState@RouteManagement@@AEAAXXZ; RouteManagement::BadConnectionState::HandlePowerStateChange(void)
0x18005bcb5  cmp     byte ptr [rdi+60h], 0
0x18005bcb9  jnz     short loc_18005BCD0
0x18005bcbb  mov     dword ptr [rdi+38h], 2
0x18005bcc2  inc     dword ptr [rdi+58h]
0x18005bcc5  mov     [rdi+4Ch], r15d
0x18005bcc9  mov     [rdi+50h], ebx
0x18005bccc  mov     [rdi+54h], r14d
0x18005bcd0  mov     rcx, [rsp+0D8h+lpCriticalSection]; lpCriticalSection
0x18005bcd5  test    rcx, rcx
0x18005bcd8  jz      short loc_18005BCE1
0x18005bcda  call    cs:__imp_LeaveCriticalSection
0x18005bce0  nop
0x18005bce1  jmp     loc_18005C0F3
0x18005bce6  mov     [rsp+0D8h+var_50], rcx
0x18005bcee  lea     rcx, [rsp+0D8h+var_50]
0x18005bcf6  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18005bcfb  nop
0x18005bcfc  cmp     dword ptr [rdi+38h], 2
0x18005bd00  jnz     short loc_18005BD0E
0x18005bd02  xor     r12b, r12b
0x18005bd05  lea     rsi, aOnecoreuapNetW_16; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005bd0c  jmp     short loc_18005BD7C
0x18005bd0e  mov     eax, cs:dword_18013A120
0x18005bd14  cmp     eax, 5
0x18005bd17  jbe     short loc_18005BD68
0x18005bd19  mov     [rsp+0D8h+lpCriticalSection], rdi
0x18005bd1e  lea     rax, aBadconnections_7; "BadConnectionState::InterfaceInBadState"
0x18005bd25  mov     [rsp+0D8h+var_90], rax
0x18005bd2a  lea     rsi, aOnecoreuapNetW_16; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005bd31  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rsi
0x18005bd39  lea     rax, [rsp+0D8h+lpCriticalSection]
0x18005bd3e  mov     [rsp+0D8h+var_A8], rax
0x18005bd43  lea     rax, [rsp+0D8h+var_90]
0x18005bd48  mov     [rsp+0D8h+var_B0], rax
0x18005bd4d  lea     rax, [rsp+0D8h+pftDueTime]
0x18005bd55  mov     [rsp+0D8h+var_B8], rax
0x18005bd5a  lea     rdx, byte_18011B961
0x18005bd61  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x18005bd66  jmp     short loc_18005BD6F
0x18005bd68  lea     rsi, aOnecoreuapNetW_16; "onecoreuap\\net\\wcm\\service\\base\\ro"...
0x18005bd6f  mov     r12b, 1
0x18005bd72  mov     dword ptr [rdi+38h], 2
0x18005bd79  inc     dword ptr [rdi+58h]
0x18005bd7c  cmp     [rdi+50h], ebx
0x18005bd7f  jz      short loc_18005BDD4
0x18005bd81  mov     eax, cs:dword_18013A120
0x18005bd87  cmp     eax, 5
0x18005bd8a  jbe     short loc_18005BDD1
0x18005bd8c  mov     dword ptr [rsp+0D8h+lpCriticalSection], ebx
0x18005bd90  lea     rax, aBadconnections_9; "BadConnectionState::InterfaceInBadState"...
0x18005bd97  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18005bd9f  mov     [rsp+0D8h+var_90], rsi
0x18005bda4  lea     rax, [rsp+0D8h+lpCriticalSection]
0x18005bda9  mov     [rsp+0D8h+var_A8], rax
0x18005bdae  lea     rax, [rsp+0D8h+pftDueTime]
0x18005bdb6  mov     [rsp+0D8h+var_B0], rax
0x18005bdbb  lea     rax, [rsp+0D8h+var_90]
0x18005bdc0  mov     [rsp+0D8h+var_B8], rax
0x18005bdc5  lea     rdx, dword_18011B99C
0x18005bdcc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005bdd1  mov     [rdi+50h], ebx
0x18005bdd4  cmp     [rdi+54h], r14d
0x18005bdd8  jz      short loc_18005BE2F
0x18005bdda  mov     eax, cs:dword_18013A120
0x18005bde0  cmp     eax, 5
0x18005bde3  jbe     short loc_18005BE2B
0x18005bde5  mov     dword ptr [rsp+0D8h+lpCriticalSection], r14d
0x18005bdea  lea     rax, aBadconnections_5; "BadConnectionState::InterfaceInBadState"...
0x18005bdf1  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18005bdf9  mov     [rsp+0D8h+var_90], rsi
0x18005bdfe  lea     rax, [rsp+0D8h+lpCriticalSection]
0x18005be03  mov     [rsp+0D8h+var_A8], rax
0x18005be08  lea     rax, [rsp+0D8h+pftDueTime]
0x18005be10  mov     [rsp+0D8h+var_B0], rax
0x18005be15  lea     rax, [rsp+0D8h+var_90]
0x18005be1a  mov     [rsp+0D8h+var_B8], rax
0x18005be1f  lea     rdx, qword_18011B838
0x18005be26  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005be2b  mov     [rdi+54h], r14d
0x18005be2f  cmp     [rdi+4Ch], r15d
0x18005be33  jz      loc_18005BF03
0x18005be39  mov     eax, cs:dword_18013A120
0x18005be3f  cmp     eax, 5
0x18005be42  jbe     short loc_18005BE8A
0x18005be44  mov     dword ptr [rsp+0D8h+lpCriticalSection], r15d
0x18005be49  lea     rax, aBadconnections_12; "BadConnectionState::InterfaceInBadState"...
0x18005be50  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18005be58  mov     [rsp+0D8h+var_90], rsi
0x18005be5d  lea     rax, [rsp+0D8h+lpCriticalSection]
0x18005be62  mov     [rsp+0D8h+var_A8], rax
0x18005be67  lea     rax, [rsp+0D8h+pftDueTime]
0x18005be6f  mov     [rsp+0D8h+var_B0], rax
0x18005be74  lea     rax, [rsp+0D8h+var_90]
0x18005be79  mov     [rsp+0D8h+var_B8], rax
0x18005be7e  lea     rdx, dword_18011B874
0x18005be85  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005be8a  mov     [rdi+4Ch], r15d
0x18005be8e  test    r12b, r12b
0x18005be91  jnz     short loc_18005BF08
0x18005be93  mov     ebx, [rdi+40h]
0x18005be96  call    cs:__imp_GetTickCount64
0x18005be9c  mov     rdx, rax
0x18005be9f  sub     edx, ebx; struct RouteManagement::ConnectionStateTelemetry *
0x18005bea1  xorps   xmm0, xmm0
0x18005bea4  movups  [rsp+0D8h+var_80], xmm0
0x18005bea9  mov     ecx, [rdi+48h]
0x18005beac  mov     [rsp+0D8h+var_88], ecx
0x18005beb0  mov     ecx, [rdi+58h]
0x18005beb3  mov     [rsp+0D8h+var_84], ecx
0x18005beb7  mov     rcx, [rdi]
0x18005beba  mov     qword ptr [rsp+0D8h+var_80], rcx
0x18005bebf  mov     rcx, [rdi+8]
0x18005bec3  mov     qword ptr [rsp+0D8h+var_80+8], rcx
0x18005bec8  mov     ecx, [rdi+3Ch]
0x18005becb  mov     [rsp+0D8h+var_70], ecx
0x18005becf  mov     eax, [rdi+4Ch]
0x18005bed2  mov     [rsp+0D8h+var_6C], eax
0x18005bed6  mov     eax, [rdi+50h]
0x18005bed9  mov     [rsp+0D8h+var_68], eax
0x18005bedd  mov     eax, [rdi+54h]
0x18005bee0  mov     [rsp+0D8h+var_64], eax
0x18005bee4  mov     [rsp+0D8h+var_60], edx
0x18005bee8  mov     eax, [rdi+5Ch]
0x18005beeb  mov     [rsp+0D8h+var_5C], eax
0x18005beef  mov     al, [rdi+60h]
0x18005bef2  mov     [rsp+0D8h+var_58], al
0x18005bef9  lea     rcx, [rsp+0D8h+var_88]; this
0x18005befe  call    ?TraceUpdateBadState@RouteManagement@@YAXAEBUConnectionStateTelemetry@1@@Z; RouteManagement::TraceUpdateBadState(RouteManagement::ConnectionStateTelemetry const &)
0x18005bf03  test    r12b, r12b
0x18005bf06  jz      short loc_18005BF6E
0x18005bf08  xorps   xmm0, xmm0
0x18005bf0b  movups  [rsp+0D8h+var_80], xmm0
0x18005bf10  mov     eax, [rdi+48h]
0x18005bf13  mov     [rsp+0D8h+var_88], eax
0x18005bf17  mov     eax, [rdi+58h]
0x18005bf1a  mov     [rsp+0D8h+var_84], eax
0x18005bf1e  mov     rax, [rdi]
0x18005bf21  mov     qword ptr [rsp+0D8h+var_80], rax
0x18005bf26  mov     rax, [rdi+8]
0x18005bf2a  mov     qword ptr [rsp+0D8h+var_80+8], rax
0x18005bf2f  mov     eax, [rdi+3Ch]
0x18005bf32  mov     [rsp+0D8h+var_70], eax
0x18005bf36  mov     eax, [rdi+4Ch]
0x18005bf39  mov     [rsp+0D8h+var_6C], eax
0x18005bf3d  mov     eax, [rdi+50h]
0x18005bf40  mov     [rsp+0D8h+var_68], eax
0x18005bf44  mov     eax, [rdi+54h]
0x18005bf47  mov     [rsp+0D8h+var_64], eax
0x18005bf4b  mov     [rsp+0D8h+var_60], 0
0x18005bf53  mov     eax, [rdi+5Ch]
0x18005bf56  mov     [rsp+0D8h+var_5C], eax
0x18005bf5a  mov     al, [rdi+60h]
0x18005bf5d  mov     [rsp+0D8h+var_58], al
0x18005bf64  lea     rcx, [rsp+0D8h+var_88]; this
0x18005bf69  call    ?TraceStartBadState@RouteManagement@@YAXAEBUConnectionStateTelemetry@1@@Z; RouteManagement::TraceStartBadState(RouteManagement::ConnectionStateTelemetry const &)
0x18005bf6e  lea     rbx, [rdi+68h]
0x18005bf72  cmp     qword ptr [rbx], 0
0x18005bf76  jnz     loc_18005C024
0x18005bf7c  xor     r8d, r8d; pcbe
0x18005bf7f  mov     rdx, rdi; pv
0x18005bf82  lea     rcx, ?BadStateTimerCallback@BadConnectionState@RouteManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005bf89  call    cs:__imp_CreateThreadpoolTimer
0x18005bf8f  mov     rdx, rax
0x18005bf92  mov     rcx, rbx
0x18005bf95  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005bf9a  cmp     qword ptr [rbx], 0
0x18005bf9e  setz    al
0x18005bfa1  mov     rcx, [rsp+0D8h]; this
0x18005bfa9  test    al, al
0x18005bfab  jnz     loc_18005C114
0x18005bfb1  call    cs:__imp_GetTickCount64
0x18005bfb7  mov     [rdi+40h], rax
0x18005bfbb  mov     [rsp+0D8h+lpCriticalSection], 0FFFFFFFFFECED300h
0x18005bfc4  mov     rax, [rsp+0D8h+lpCriticalSection]
0x18005bfc9  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18005bfd1  xor     r9d, r9d; msWindowLength
0x18005bfd4  xor     r8d, r8d; msPeriod
0x18005bfd7  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18005bfdf  mov     rcx, [rbx]; pti
0x18005bfe2  call    cs:__imp_SetThreadpoolTimer
0x18005bfe8  lea     r14, WPP_GLOBAL_Control
0x18005bfef  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bff6  cmp     rcx, r14
0x18005bff9  jz      short loc_18005C02B
0x18005bffb  cmp     byte ptr [rcx+19h], 4
0x18005bfff  jb      short loc_18005C02B
0x18005c001  test    byte ptr [rcx+1Ch], 1
0x18005c005  jz      short loc_18005C02B
0x18005c007  mov     edx, 0Dh
0x18005c00c  mov     r9d, 7D0h
0x18005c012  lea     r8, WPP_b117651525d03ae6d39c613c7f962000_Traceguids
0x18005c019  mov     rcx, [rcx+10h]
0x18005c01d  call    WPP_SF_d
0x18005c022  jmp     short loc_18005C02B
0x18005c024  lea     r14, WPP_GLOBAL_Control
0x18005c02b  cmp     dword ptr [rdi+3Ch], 2
0x18005c02f  jnz     loc_18005C0DF
0x18005c035  lea     rbx, [rdi+70h]
0x18005c039  cmp     qword ptr [rbx], 0
0x18005c03d  jnz     loc_18005C0DF
0x18005c043  xor     r8d, r8d; pcbe
0x18005c046  mov     rdx, rdi; pv
0x18005c049  lea     rcx, ?BadWifiLocationTimerCallback@BadConnectionState@RouteManagement@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18005c050  call    cs:__imp_CreateThreadpoolTimer
0x18005c056  mov     rdx, rax
0x18005c059  mov     rcx, rbx
0x18005c05c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18005c061  mov     rcx, [rbx]; pti
0x18005c064  test    rcx, rcx
0x18005c067  setz    al
0x18005c06a  mov     r9, [rsp+0D8h]; char *
0x18005c072  test    al, al
0x18005c074  jnz     loc_18005C121
0x18005c07a  mov     dword ptr [rsp+0D8h+lpCriticalSection+4], 0FFFFFFFFh
0x18005c082  mov     dword ptr [rsp+0D8h+lpCriticalSection], 4D2FA200h
0x18005c08a  mov     rax, [rsp+0D8h+lpCriticalSection]
0x18005c08f  mov     qword ptr [rsp+0D8h+pftDueTime.dwLowDateTime], rax
0x18005c097  xor     r9d, r9d; msWindowLength
0x18005c09a  xor     r8d, r8d; msPeriod
0x18005c09d  lea     rdx, [rsp+0D8h+pftDueTime]; pftDueTime
0x18005c0a5  call    cs:__imp_SetThreadpoolTimer
0x18005c0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c0b2  cmp     rcx, r14
0x18005c0b5  jz      short loc_18005C0DF
0x18005c0b7  cmp     byte ptr [rcx+19h], 4
0x18005c0bb  jb      short loc_18005C0DF
0x18005c0bd  test    byte ptr [rcx+1Ch], 1
0x18005c0c1  jz      short loc_18005C0DF
0x18005c0c3  mov     edx, 0Eh
0x18005c0c8  mov     r9d, 493E0h
0x18005c0ce  lea     r8, WPP_b117651525d03ae6d39c613c7f962000_Traceguids
0x18005c0d5  mov     rcx, [rcx+10h]
0x18005c0d9  call    WPP_SF_d
0x18005c0de  nop
0x18005c0df  mov     rcx, [rsp+0D8h+var_50]; lpCriticalSection
0x18005c0e7  test    rcx, rcx
0x18005c0ea  jz      short loc_18005C0F3
0x18005c0ec  call    cs:__imp_LeaveCriticalSection
0x18005c0f2  nop
0x18005c0f3  mov     rcx, [rsp+0D8h+var_40]
0x18005c0fb  xor     rcx, rsp; StackCookie
0x18005c0fe  call    __security_check_cookie
0x18005c103  add     rsp, 0A8h
0x18005c10a  pop     r15
0x18005c10c  pop     r14
0x18005c10e  pop     r12
0x18005c110  pop     rdi
0x18005c111  pop     rsi
0x18005c112  pop     rbx
0x18005c113  retn
0x18005c114  mov     r8, rsi; unsigned int
0x18005c117  mov     edx, 0E8h; void *
0x18005c11c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005c121  mov     r8, rsi; unsigned int
0x18005c124  mov     edx, 0F9h; void *
0x18005c129  mov     rcx, r9; this
0x18005c12c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
