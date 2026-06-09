# Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(ulong,Microsoft::Diagnostics::EnumDetails::ExternalHangBucket,_CONTEXT const &)

- ea: `0x180040454`
- end: `0x180040a30`
- name: `??0ThreadMonitor@UtcWatchdog@Diagnostics@Microsoft@@QEAA@KVExternalHangBucket@EnumDetails@23@AEBU_CONTEXT@@@Z`
- size: `1500`
- prototype: `__int64(void)`
- caller_count: `113`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005ff28`
- `0x180061fa0`
- `0x180062cc0`
- `0x1800cc550`
- `0x1801674fc`
- `0x1801900b0`
- `0x180194dac`
- `0x1801beccc`
- `0x1801bf0a4`
- `0x1801bf350`
- `0x1801bf874`
- `0x1801bfdf0`
- `0x1801c0430`
- `0x1801deafc`
- `0x180213898`
- `0x18022dd54`
- `0x1802a3078`
- `0x1802a35e4`
- `0x1802a37a0`
- `0x1802a43e0`
- `0x1802a45f0`
- `0x1802a5220`
- `0x1802a562c`
- `0x1802a6bc0`
- `0x1802a6c80`
- `0x1802a6d30`
- `0x1802a6e00`
- `0x1802a6ec0`
- `0x1802a6f80`
- `0x1802a7040`
- `0x1802a70f0`
- `0x1802a7200`
- `0x1802a72d0`
- `0x1802a7390`
- `0x1802a7450`
- `0x1802a7520`
- `0x1802a75e0`
- `0x1802a76c0`
- `0x1802a77b0`
- `0x1802a7890`
- `0x1802a7980`
- `0x1802a7a30`
- `0x1802a7b40`
- `0x1802a7c60`
- `0x1802a7d80`
- `0x1802a7e90`
- `0x1802a7fb0`
- `0x1802a80d0`
- `0x1802a8190`
- `0x1802a8260`

## callees

- `0x18001cf30`
- `0x180040454`
- `0x180040a38`
- `0x180040b10`
- `0x180040b90`
- `0x1800a0d08`
- `0x1800d0d9c`
- `0x1800d2ee8`
- `0x1800dbc08`
- `0x18012de40`
- `0x18012eb08`
- `0x180190328`
- `0x1801b2b24`
- `0x1801b4d34`
- `0x1801b79d8`
- `0x1801b7e40`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18004063a`
- `msvcp_win!_Mtx_unlock` at `0x18004063a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040a06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040a18`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040a06`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040a18`
- `msvcp_win!_Mtx_lock` at `0x1800405d5`
- `msvcp_win!_Mtx_lock` at `0x1800405d5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180040990`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180040990`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040721`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040721`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800406ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800406ec`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180040575`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800406c8`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180040575`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800406c8`

## string_xrefs

- `0x180040955`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`
- `0x1800409a9`: `onecore\base\telemetry\utc\service\include\UtcWatchdog.h`
- `0x180040975`: `onecore\base\telemetry\utc\service\engine\utcwatchdog.cpp`
- `0x1800409c2`: `onecore\base\telemetry\utc\service\engine\utcwatchdog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(
        __int64 a1,
        unsigned int a2,
        unsigned __int8 a3,
        const char *a4)
{
  const char *v4; // rsi
  __int64 v7; // rbx
  int v8; // r13d
  __int64 v9; // r14
  __int64 i; // rbx
  const char *v11; // r9
  char v12; // r15
  char v13; // al
  __int64 v14; // rbx
  __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  _OWORD *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  _OWORD *v22; // rax
  _OWORD *v23; // rcx
  int ServiceProcessId; // eax
  __int64 v26; // rdx
  unsigned __int64 UnbiasedTime; // [rsp+20h] [rbp-E0h] BYREF
  unsigned __int64 v28; // [rsp+28h] [rbp-D8h]
  unsigned int v29; // [rsp+30h] [rbp-D0h]
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h]
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  signed __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  char v35; // [rsp+70h] [rbp-90h]
  _QWORD v36[10]; // [rsp+80h] [rbp-80h]
  _BYTE v37[1232]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v38; // [rsp+5A0h] [rbp+4A0h]
  __int64 v39; // [rsp+5A8h] [rbp+4A8h]
  __int64 v40; // [rsp+5B0h] [rbp+4B0h]
  __int64 v41; // [rsp+5B8h] [rbp+4B8h]
  wil::details::in1diag3 *retaddr; // [rsp+618h] [rbp+518h]

  v4 = a4;
  v29 = a2;
  *(_QWORD *)a1 = 0;
  *(_WORD *)(a1 + 8) = 0;
  if ( _InterlockedCompareExchange64((_QWORD *)&xmmword_18043C000 + 1, 0, 0) )
  {
    if ( !_InterlockedCompareExchange64((_QWORD *)&xmmword_18043C000 + 1, 0, 0) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x76,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\LifetimeManager.h",
        a4);
    v7 = *((_QWORD *)&xmmword_18043C000 + 1);
    v31 = *((_QWORD *)&xmmword_18043C000 + 1);
    v36[0] = &Src;
    v36[1] = 0;
    v36[2] = &Src;
    v36[3] = 0;
    v36[4] = L"UserManager";
    v36[5] = 11;
    v36[6] = L"netprofm";
    v36[7] = 8;
    v36[8] = L"nsi";
    v36[9] = 3;
    v8 = 0;
    LODWORD(UnbiasedTime) = 0;
    if ( a3 == 1 )
    {
      if ( *(_BYTE *)(*((_QWORD *)&xmmword_18043C000 + 1) + 185LL) )
        v8 = 4;
    }
    else if ( a3 && *(_BYTE *)(*((_QWORD *)&xmmword_18043C000 + 1) + 184LL) )
    {
      v32 = *(_OWORD *)&v36[2 * a3];
      ServiceProcessId = Microsoft::Diagnostics::Utils::Os::GetServiceProcessId(&v32, &UnbiasedTime);
      if ( ServiceProcessId < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcwatchdog.cpp",
          (const char *)(unsigned int)ServiceProcessId,
          UnbiasedTime);
      v8 = UnbiasedTime;
    }
    v9 = v7 + 416;
    *(_QWORD *)&v32 = v7 + 416;
    BYTE8(v32) = 0;
    if ( *(_BYTE *)(v7 + 609) )
    {
      Sleep(0x57E40u);
      wil::details::in1diag3::FailFast_Win32(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcWatchdog.h",
        (const char *)0x5B4,
        UnbiasedTime);
    }
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v28 = UnbiasedTime / 0x2710;
    for ( i = 60000; ; i = 60000 - v26 )
    {
      if ( !v9 )
        std::_Throw_system_error(1);
      std::chrono::steady_clock::now(&v33);
      UnbiasedTime = v33;
      if ( i > 0 )
      {
        if ( v33 >= 0x7FFFFFFFFFFFFFFFLL - 1000000 * i )
          UnbiasedTime = 0x7FFFFFFFFFFFFFFFLL;
        else
          UnbiasedTime = 1000000 * i + v33;
      }
      v34 = v9;
      if ( _Mtx_lock((_Mtx_t)v9) )
        goto LABEL_47;
      if ( *(_DWORD *)(v9 + 76) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v9 + 76) = 2147483646;
        std::_Throw_Cpp_error(6);
        __debugbreak();
LABEL_47:
        std::_Throw_Cpp_error(5);
        __debugbreak();
        std::_Throw_system_error(36);
      }
      v35 = 1;
      do
      {
        if ( !*(_DWORD *)(v9 + 152) )
          goto LABEL_16;
      }
      while ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                              v9 + 80,
                              &v34,
                              &UnbiasedTime) != 1 );
      if ( !*(_DWORD *)(v9 + 152) )
      {
LABEL_16:
        *(_DWORD *)(v9 + 152) = -1;
        _Mtx_unlock((_Mtx_t)v9);
        v12 = 1;
        BYTE8(v32) = 1;
        v13 = 1;
        goto LABEL_17;
      }
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v34);
      v12 = 0;
      BYTE8(v32) = 0;
      v26 = Microsoft::Diagnostics::Utils::Time::QueryUbiTime() / 0x2710 - v28;
      if ( v26 > 60000 )
        break;
    }
    v13 = 0;
LABEL_17:
    if ( !v13 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcwatchdog.cpp",
        v11);
    v14 = v31;
    memset_0(v37, 0, sizeof(v37));
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    std::list<Microsoft::Diagnostics::UtcWatchdog::ThreadTimeoutSpec>::push_front(v14 + 576, v37);
    std::list<Microsoft::Diagnostics::UtcWatchdog::ThreadTimeoutSpec>::begin(v14 + 576, &v30);
    v15 = v30;
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v28 = UnbiasedTime / 0x2710;
    *(_QWORD *)(v15 + 1256) = GetTickCount64();
    v16 = v28;
    *(_QWORD *)(v15 + 1264) = v28;
    if ( v29 )
      v17 = v16 + v29;
    else
      v17 = -1;
    *(_QWORD *)(v15 + 1272) = v17;
    *(_DWORD *)(v15 + 1248) = GetCurrentThreadId();
    if ( v8 )
      *(_DWORD *)std::map<unsigned long,Microsoft::Diagnostics::UtcWatchdog::ThreadState>::operator[](
                   v31 + 592,
                   v30 + 1248) = v8;
    if ( v12 )
      std::timed_mutex::unlock((_Mtx_t)v9);
    v18 = v30;
    *(_QWORD *)a1 = v30;
    v19 = v37;
    v20 = 9;
    v21 = 9;
    do
    {
      *v19 = *(_OWORD *)v4;
      v19[1] = *((_OWORD *)v4 + 1);
      v19[2] = *((_OWORD *)v4 + 2);
      v19[3] = *((_OWORD *)v4 + 3);
      v19[4] = *((_OWORD *)v4 + 4);
      v19[5] = *((_OWORD *)v4 + 5);
      v19[6] = *((_OWORD *)v4 + 6);
      v19[7] = *((_OWORD *)v4 + 7);
      v19 += 8;
      v4 += 128;
      --v21;
    }
    while ( v21 );
    *v19 = *(_OWORD *)v4;
    v19[1] = *((_OWORD *)v4 + 1);
    v19[2] = *((_OWORD *)v4 + 2);
    v19[3] = *((_OWORD *)v4 + 3);
    v19[4] = *((_OWORD *)v4 + 4);
    v22 = (_OWORD *)(v18 + 16);
    v23 = v37;
    do
    {
      *v22 = *v23;
      v22[1] = v23[1];
      v22[2] = v23[2];
      v22[3] = v23[3];
      v22[4] = v23[4];
      v22[5] = v23[5];
      v22[6] = v23[6];
      v22[7] = v23[7];
      v22 += 8;
      v23 += 8;
      --v20;
    }
    while ( v20 );
    *v22 = *v23;
    v22[1] = v23[1];
    v22[2] = v23[2];
    v22[3] = v23[3];
    v22[4] = v23[4];
    *(_BYTE *)(a1 + 9) = a3;
    *(_BYTE *)(a1 + 8) = 1;
  }
  return a1;
}

```

## disassembly

```asm
0x180040454  push    rbp
0x180040456  push    rbx
0x180040457  push    rsi
0x180040458  push    rdi
0x180040459  push    r12
0x18004045b  push    r13
0x18004045d  push    r14
0x18004045f  push    r15
0x180040461  lea     rbp, [rsp-4D8h]
0x180040469  sub     rsp, 5D8h
0x180040470  mov     rax, cs:__security_cookie
0x180040477  xor     rax, rsp
0x18004047a  mov     [rbp+510h+var_50], rax
0x180040481  mov     rsi, r9
0x180040484  movzx   edi, r8b
0x180040488  mov     [rsp+610h+var_5E0], edx
0x18004048c  mov     r12, rcx
0x18004048f  xor     r15d, r15d
0x180040492  mov     [rcx], r15
0x180040495  mov     [rcx+8], r15w
0x18004049a  mov     ecx, r15d
0x18004049d  xor     eax, eax
0x18004049f  lock cmpxchg qword ptr cs:xmmword_18043C000+8, rcx
0x1800404a8  jz      loc_180040856
0x1800404ae  xor     eax, eax
0x1800404b0  lock cmpxchg qword ptr cs:xmmword_18043C000+8, rcx
0x1800404b9  setz    al
0x1800404bc  mov     rcx, [rbp+518h]; this
0x1800404c3  test    al, al
0x1800404c5  jnz     loc_180040955
0x1800404cb  mov     rbx, qword ptr cs:xmmword_18043C000+8
0x1800404d2  mov     [rsp+610h+var_5D0], rbx
0x1800404d7  lea     rax, Src
0x1800404de  mov     qword ptr [rbp+510h+var_590], rax
0x1800404e2  mov     qword ptr [rbp+510h+var_590+8], r15
0x1800404e6  mov     [rbp+510h+var_580], rax
0x1800404ea  mov     [rbp+510h+var_578], r15
0x1800404ee  lea     rax, aUsermanager_0; "UserManager"
0x1800404f5  mov     [rbp+510h+var_570], rax
0x1800404f9  mov     [rbp+510h+var_568], 0Bh
0x180040501  lea     rax, aNetprofm; "netprofm"
0x180040508  mov     [rbp+510h+var_560], rax
0x18004050c  mov     [rbp+510h+var_558], 8
0x180040514  lea     rax, aNsi; "nsi"
0x18004051b  mov     [rbp+510h+var_550], rax
0x18004051f  mov     [rbp+510h+var_548], 3
0x180040527  mov     r13d, r15d
0x18004052a  mov     dword ptr [rsp+610h+UnbiasedTime], r15d; unsigned int
0x18004052f  cmp     dil, 1
0x180040533  jnz     loc_1800408B1
0x180040539  mov     al, [rbx+0B9h]
0x18004053f  test    al, al
0x180040541  jnz     loc_180040967
0x180040547  lea     r14, [rbx+1A0h]
0x18004054e  mov     qword ptr [rsp+610h+var_5C0], r14
0x180040553  mov     byte ptr [rsp+610h+var_5C0+8], r15b
0x180040558  mov     al, [rbx+261h]
0x18004055e  nop
0x18004055f  test    al, al
0x180040561  jnz     loc_18004098B
0x180040567  mov     [rsp+610h+UnbiasedTime], 0
0x180040570  lea     rcx, [rsp+610h+UnbiasedTime]; UnbiasedTime
0x180040575  call    cs:__imp_QueryUnbiasedInterruptTime
0x18004057c  nop     dword ptr [rax+rax+00h]
0x180040581  mov     rax, 346DC5D63886594Bh
0x18004058b  mul     [rsp+610h+UnbiasedTime]
0x180040590  shr     rdx, 0Bh
0x180040594  mov     [rsp+610h+var_5E8], rdx
0x180040599  mov     ebx, 0EA60h
0x18004059e  test    r14, r14
0x1800405a1  jz      loc_180040906
0x1800405a7  test    r15b, r15b
0x1800405aa  jnz     loc_180040A25
0x1800405b0  lea     rcx, [rsp+610h+var_5B0]
0x1800405b5  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800405ba  mov     rax, [rsp+610h+var_5B0]
0x1800405bf  mov     [rsp+610h+UnbiasedTime], rax
0x1800405c4  test    rbx, rbx
0x1800405c7  jg      loc_18004087D
0x1800405cd  mov     [rsp+610h+var_5A8], r14
0x1800405d2  mov     rcx, r14; _Mtx_t
0x1800405d5  call    cs:__imp__Mtx_lock
0x1800405dc  nop     dword ptr [rax+rax+00h]
0x1800405e1  test    eax, eax
0x1800405e3  jnz     loc_180040A13
0x1800405e9  cmp     dword ptr [r14+4Ch], 7FFFFFFFh
0x1800405f1  jz      loc_1800409F9
0x1800405f7  mov     [rsp+610h+var_5A0], 1
0x1800405fc  cmp     dword ptr [r14+98h], 0
0x180040604  jz      short loc_18004062C
0x180040606  lea     r8, [rsp+610h+UnbiasedTime]
0x18004060b  lea     rdx, [rsp+610h+var_5A8]
0x180040610  lea     rcx, [r14+50h]
0x180040614  call    ??$wait_until@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@condition_variable@std@@QEAA?AW4cv_status@1@AEAV?$unique_lock@Vmutex@std@@@1@AEBV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@chrono@1@@Z; std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::unique_lock<std::mutex> &,std::chrono::time_point<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>> const &)
0x180040619  cmp     eax, 1
0x18004061c  jnz     short loc_1800405FC
0x18004061e  cmp     dword ptr [r14+98h], 0
0x180040626  jnz     loc_180040911
0x18004062c  mov     dword ptr [r14+98h], 0FFFFFFFFh
0x180040637  mov     rcx, r14; _Mtx_t
0x18004063a  call    cs:__imp__Mtx_unlock
0x180040641  nop     dword ptr [rax+rax+00h]
0x180040646  mov     r15b, 1
0x180040649  mov     byte ptr [rsp+610h+var_5C0+8], r15b
0x18004064e  mov     al, r15b
0x180040651  mov     rcx, [rbp+518h]; this
0x180040658  test    al, al
0x18004065a  jz      loc_1800409C2
0x180040660  mov     rbx, [rsp+610h+var_5D0]
0x180040665  xor     edx, edx; Val
0x180040667  mov     r8d, 4D0h; Size
0x18004066d  lea     rcx, [rbp+510h+var_540]; void *
0x180040671  call    memset_0
0x180040676  xor     ecx, ecx
0x180040678  mov     [rbp+510h+var_70], rcx
0x18004067f  mov     [rbp+510h+var_68], rcx
0x180040686  mov     [rbp+510h+var_60], rcx
0x18004068d  mov     [rbp+510h+var_58], rcx
0x180040694  lea     rdx, [rbp+510h+var_540]
0x180040698  lea     rcx, [rbx+240h]
0x18004069f  call    ?push_front@?$list@UThreadTimeoutSpec@UtcWatchdog@Diagnostics@Microsoft@@V?$allocator@UThreadTimeoutSpec@UtcWatchdog@Diagnostics@Microsoft@@@std@@@std@@QEAAX$$QEAUThreadTimeoutSpec@UtcWatchdog@Diagnostics@Microsoft@@@Z; std::list<Microsoft::Diagnostics::UtcWatchdog::ThreadTimeoutSpec>::push_front(Microsoft::Diagnostics::UtcWatchdog::ThreadTimeoutSpec &&)
0x1800406a4  lea     rdx, [rsp+610h+var_5D8]
0x1800406a9  lea     rcx, [rbx+240h]
0x1800406b0  call    ?begin@?$list@UThreadTimeoutSpec@UtcWatchdog@Diagnostics@Microsoft@@V?$allocator@UThreadTimeoutSpec@UtcWatchdog@Diagnostics@Microsoft@@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@UThreadTimeoutSpec@UtcWatchdog@Diagnostics@Microsoft@@@std@@@std@@@2@XZ; std::list<Microsoft::Diagnostics::UtcWatchdog::ThreadTimeoutSpec>::begin(void)
0x1800406b5  mov     rbx, [rsp+610h+var_5D8]
0x1800406ba  mov     [rsp+610h+UnbiasedTime], 0
0x1800406c3  lea     rcx, [rsp+610h+UnbiasedTime]; UnbiasedTime
0x1800406c8  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800406cf  nop     dword ptr [rax+rax+00h]
0x1800406d4  mov     rax, 346DC5D63886594Bh
0x1800406de  mul     [rsp+610h+UnbiasedTime]
0x1800406e3  shr     rdx, 0Bh
0x1800406e7  mov     [rsp+610h+var_5E8], rdx
0x1800406ec  call    cs:__imp_GetTickCount64
0x1800406f3  nop     dword ptr [rax+rax+00h]
0x1800406f8  mov     [rbx+4E8h], rax
0x1800406ff  mov     rcx, [rsp+610h+var_5E8]
0x180040704  mov     [rbx+4F0h], rcx
0x18004070b  mov     eax, [rsp+610h+var_5E0]
0x18004070f  test    eax, eax
0x180040711  jz      loc_1800408FD
0x180040717  add     rax, rcx
0x18004071a  mov     [rbx+4F8h], rax
0x180040721  call    cs:__imp_GetCurrentThreadId
0x180040728  nop     dword ptr [rax+rax+00h]
0x18004072d  mov     [rbx+4E0h], eax
0x180040733  test    r13d, r13d
0x180040736  jnz     loc_1800409D4
0x18004073c  test    r15b, r15b
0x18004073f  jz      short loc_18004074A
0x180040741  mov     rcx, r14; this
0x180040744  call    ?unlock@timed_mutex@std@@QEAAXXZ; std::timed_mutex::unlock(void)
0x180040749  nop
0x18004074a  mov     rcx, [rsp+610h+var_5D8]
0x18004074f  mov     [r12], rcx
0x180040753  lea     rax, [rbp+510h+var_540]
0x180040757  mov     edx, 9
0x18004075c  mov     r8d, edx
0x18004075f  lea     r9d, [rdx+77h]
0x180040763  movups  xmm0, xmmword ptr [rsi]
0x180040766  movups  xmmword ptr [rax], xmm0
0x180040769  movups  xmm1, xmmword ptr [rsi+10h]
0x18004076d  movups  xmmword ptr [rax+10h], xmm1
0x180040771  movups  xmm0, xmmword ptr [rsi+20h]
0x180040775  movups  xmmword ptr [rax+20h], xmm0
0x180040779  movups  xmm1, xmmword ptr [rsi+30h]
0x18004077d  movups  xmmword ptr [rax+30h], xmm1
0x180040781  movups  xmm0, xmmword ptr [rsi+40h]
0x180040785  movups  xmmword ptr [rax+40h], xmm0
0x180040789  movups  xmm1, xmmword ptr [rsi+50h]
0x18004078d  movups  xmmword ptr [rax+50h], xmm1
0x180040791  movups  xmm0, xmmword ptr [rsi+60h]
0x180040795  movups  xmmword ptr [rax+60h], xmm0
0x180040799  movups  xmm1, xmmword ptr [rsi+70h]
0x18004079d  movups  xmmword ptr [rax+70h], xmm1
0x1800407a1  add     rax, r9
0x1800407a4  add     rsi, r9
0x1800407a7  sub     r8, 1
0x1800407ab  jnz     short loc_180040763
0x1800407ad  movups  xmm0, xmmword ptr [rsi]
0x1800407b0  movups  xmmword ptr [rax], xmm0
0x1800407b3  movups  xmm1, xmmword ptr [rsi+10h]
0x1800407b7  movups  xmmword ptr [rax+10h], xmm1
0x1800407bb  movups  xmm0, xmmword ptr [rsi+20h]
0x1800407bf  movups  xmmword ptr [rax+20h], xmm0
0x1800407c3  movups  xmm1, xmmword ptr [rsi+30h]
0x1800407c7  movups  xmmword ptr [rax+30h], xmm1
0x1800407cb  movups  xmm0, xmmword ptr [rsi+40h]
0x1800407cf  movups  xmmword ptr [rax+40h], xmm0
0x1800407d3  lea     rax, [rcx+10h]
0x1800407d7  lea     rcx, [rbp+510h+var_540]
0x1800407db  movups  xmm0, xmmword ptr [rcx]
0x1800407de  movups  xmmword ptr [rax], xmm0
0x1800407e1  movups  xmm1, xmmword ptr [rcx+10h]
0x1800407e5  movups  xmmword ptr [rax+10h], xmm1
0x1800407e9  movups  xmm0, xmmword ptr [rcx+20h]
0x1800407ed  movups  xmmword ptr [rax+20h], xmm0
0x1800407f1  movups  xmm1, xmmword ptr [rcx+30h]
0x1800407f5  movups  xmmword ptr [rax+30h], xmm1
0x1800407f9  movups  xmm0, xmmword ptr [rcx+40h]
0x1800407fd  movups  xmmword ptr [rax+40h], xmm0
0x180040801  movups  xmm1, xmmword ptr [rcx+50h]
0x180040805  movups  xmmword ptr [rax+50h], xmm1
0x180040809  movups  xmm0, xmmword ptr [rcx+60h]
0x18004080d  movups  xmmword ptr [rax+60h], xmm0
0x180040811  movups  xmm1, xmmword ptr [rcx+70h]
0x180040815  movups  xmmword ptr [rax+70h], xmm1
0x180040819  add     rax, r9
0x18004081c  add     rcx, r9
0x18004081f  sub     rdx, 1
0x180040823  jnz     short loc_1800407DB
0x180040825  movups  xmm0, xmmword ptr [rcx]
0x180040828  movups  xmmword ptr [rax], xmm0
0x18004082b  movups  xmm1, xmmword ptr [rcx+10h]
0x18004082f  movups  xmmword ptr [rax+10h], xmm1
0x180040833  movups  xmm0, xmmword ptr [rcx+20h]
0x180040837  movups  xmmword ptr [rax+20h], xmm0
0x18004083b  movups  xmm1, xmmword ptr [rcx+30h]
0x18004083f  movups  xmmword ptr [rax+30h], xmm1
0x180040843  movups  xmm0, xmmword ptr [rcx+40h]
0x180040847  movups  xmmword ptr [rax+40h], xmm0
0x18004084b  mov     [r12+9], dil
0x180040850  mov     byte ptr [r12+8], 1
0x180040856  mov     rax, r12
0x180040859  mov     rcx, [rbp+510h+var_50]
0x180040860  xor     rcx, rsp; StackCookie
0x180040863  call    __security_check_cookie
0x180040868  add     rsp, 5D8h
0x18004086f  pop     r15
0x180040871  pop     r14
0x180040873  pop     r13
0x180040875  pop     r12
0x180040877  pop     rdi
0x180040878  pop     rsi
0x180040879  pop     rbx
0x18004087a  pop     rbp
0x18004087b  retn
0x18004087d  imul    rdx, rbx, 0F4240h
0x180040884  mov     r8, 7FFFFFFFFFFFFFFFh
0x18004088e  mov     rcx, r8
0x180040891  sub     rcx, rdx
0x180040894  cmp     rax, rcx
0x180040897  jge     short loc_1800408A7
0x180040899  lea     rcx, [rdx+rax]
0x18004089d  mov     [rsp+610h+UnbiasedTime], rcx
0x1800408a2  jmp     loc_1800405CD
0x1800408a7  mov     [rsp+610h+UnbiasedTime], r8
0x1800408ac  jmp     loc_1800405CD
0x1800408b1  test    r8b, r8b
0x1800408b4  jz      loc_180040547
0x1800408ba  mov     al, [rbx+0B8h]
0x1800408c0  test    al, al
0x1800408c2  jz      loc_180040547
0x1800408c8  mov     rax, rdi
0x1800408cb  add     rax, rax
0x1800408ce  movups  xmm0, [rbp+rax*8+510h+var_590]
0x1800408d3  movdqu  [rsp+610h+var_5C0], xmm0
0x1800408d9  lea     rdx, [rsp+610h+UnbiasedTime]
0x1800408de  lea     rcx, [rsp+610h+var_5C0]
0x1800408e3  call    ?GetServiceProcessId@Os@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAK@Z; Microsoft::Diagnostics::Utils::Os::GetServiceProcessId(std::wstring_view,ulong &)
0x1800408e8  mov     rcx, [rbp+518h]; this
0x1800408ef  test    eax, eax
0x1800408f1  js      short loc_180040972
0x1800408f3  mov     r13d, dword ptr [rsp+610h+UnbiasedTime]
0x1800408f8  jmp     loc_180040547
0x1800408fd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040901  jmp     loc_18004071A
0x180040906  mov     ecx, 1
0x18004090b  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x180040911  lea     rcx, [rsp+610h+var_5A8]
0x180040916  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18004091b  xor     r15b, r15b
0x18004091e  mov     byte ptr [rsp+610h+var_5C0+8], r15b
0x180040923  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x180040928  mov     rcx, rax
0x18004092b  mov     rax, 346DC5D63886594Bh
0x180040935  mul     rcx
0x180040938  shr     rdx, 0Bh
0x18004093c  sub     rdx, [rsp+610h+var_5E8]
0x180040941  mov     eax, 0EA60h
0x180040946  cmp     rdx, rax
0x180040949  jg      short loc_1800409BB
0x18004094b  mov     ebx, eax
0x18004094d  sub     rbx, rdx
0x180040950  jmp     loc_18004059E
0x180040955  lea     r8, aOnecoreBaseTel_20; "onecore\\base\\telemetry\\utc\\service"...
0x18004095c  mov     edx, 76h ; 'v'; void *
0x180040961  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180040967  mov     r13d, 4
0x18004096d  jmp     loc_180040547
0x180040972  mov     r9d, eax; char *
0x180040975  lea     r8, aOnecoreBaseTel_69; "onecore\\base\\telemetry\\utc\\service"...
0x18004097c  mov     edx, 178h; void *
0x180040981  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040986  jmp     loc_1800408F3
0x18004098b  mov     ecx, 57E40h; dwMilliseconds
0x180040990  call    cs:__imp_Sleep
0x180040997  nop     dword ptr [rax+rax+00h]
0x18004099c  mov     rcx, [rbp+518h]; this
0x1800409a3  mov     r9d, 5B4h; char *
  ... truncated ...
```
