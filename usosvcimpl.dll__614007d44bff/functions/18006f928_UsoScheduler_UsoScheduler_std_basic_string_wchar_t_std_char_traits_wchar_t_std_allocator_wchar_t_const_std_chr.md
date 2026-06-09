# UsoScheduler::UsoScheduler(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::chrono::duration<__int64,std::ratio<1,1>> const &,bool,std::function<void (void)> &&)

- ea: `0x18006f928`
- end: `0x18006fbbc`
- name: `??0UsoScheduler@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@2@_N$$QEAV?$function@$$A6AXXZ@2@@Z`
- size: `660`
- prototype: `UsoScheduler *__fastcall(UsoScheduler *this, __int64, _QWORD *, char, __int64)`
- caller_count: `12`
- callee_count: `7`
- tags: `service_task, installer_update`

## callers

- `0x180017158`
- `0x1800187f0`
- `0x18001b0d4`
- `0x18001b2bc`
- `0x18001b43c`
- `0x18001b554`
- `0x18001b66c`
- `0x18001b784`
- `0x18001b89c`
- `0x18001b9a8`
- `0x18001bac0`
- `0x18001bbd8`

## callees

- `0x180010f24`
- `0x180011320`
- `0x18006f928`
- `0x18006ffe4`
- `0x18007023c`
- `0x18007039c`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fb5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006fb5e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006f95d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18006f95d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa1f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006fa1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006faed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006fa6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006faed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fa81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fb1d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fa81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006fb1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18006fab7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18006fab7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006fb00`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006fb00`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006fadb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006fadb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18006faa0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18006faa0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18006fa79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18006fa79`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006fb15`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006fb15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006fb0c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006fb0c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18006fa5c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18006fa5c`

## string_xrefs

- `0x18006fb3b`: `Scheduled timer: Name={}`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
UsoScheduler *__fastcall UsoScheduler::UsoScheduler(UsoScheduler *this, __int64 a2, _QWORD *a3, char a4, __int64 a5)
{
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  const char *v13; // r9
  struct _TP_POOL *Threadpool; // r14
  struct _TP_POOL *v15; // r15
  DWORD LastError; // ebx
  const char *v17; // r9
  const char *v18; // r9
  PTP_TIMER ThreadpoolTimer; // r14
  struct _TP_TIMER *v20; // rsi
  DWORD v21; // ebx
  _QWORD v23[3]; // [rsp+30h] [rbp-41h] BYREF
  _BYTE v24[56]; // [rsp+48h] [rbp-29h] BYREF
  _BYTE *v25; // [rsp+80h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  v23[2] = this;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this, 0, 0);
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  std::wstring::wstring((__int64)this + 128, a2);
  v25 = 0;
  v9 = *(_QWORD *)(a5 + 56);
  if ( v9 )
  {
    if ( v9 == a5 )
    {
      v25 = (_BYTE *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v9 + 8LL))(v9, v24);
      v11 = *(_QWORD *)(a5 + 56);
      if ( !v11 )
        goto LABEL_7;
      LOBYTE(v10) = v11 != a5;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, v10);
    }
    else
    {
      v25 = *(_BYTE **)(a5 + 56);
    }
    *(_QWORD *)(a5 + 56) = 0;
  }
LABEL_7:
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 34) = wistd::__function::__func<std::function<void (void)>,void (void)>::__func<std::function<void (void)>,void (void)>(
                             (char *)this + 168,
                             v24);
  if ( v25 )
  {
    LOBYTE(v12) = v25 != v24;
    (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v25 + 32LL))(v25, v12);
  }
  *((_QWORD *)this + 35) = *a3;
  *((_BYTE *)this + 288) = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  *((_DWORD *)this + 10) = 3;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_DWORD *)this + 25) = 1;
  *((_DWORD *)this + 26) = 72;
  Threadpool = CreateThreadpool(0);
  v15 = (struct _TP_POOL *)*((_QWORD *)this + 14);
  if ( v15 )
  {
    LastError = GetLastError();
    CloseThreadpool(v15);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 14) = Threadpool;
  if ( !Threadpool )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x39,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\usoscheduler\\UsoScheduler.cpp",
      v13);
  SetThreadpoolThreadMaximum(Threadpool, 1u);
  if ( !SetThreadpoolThreadMinimum(*((PTP_POOL *)this + 14), 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x3D,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\usoscheduler\\UsoScheduler.cpp",
      v17);
  *((_QWORD *)this + 6) = *((_QWORD *)this + 14);
  ThreadpoolTimer = CreateThreadpoolTimer(ThreadPoolTimerCallback, this, (PTP_CALLBACK_ENVIRON)((char *)this + 40));
  v20 = (struct _TP_TIMER *)*((_QWORD *)this + 15);
  if ( v20 )
  {
    v21 = GetLastError();
    SetThreadpoolTimer(v20, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v20, 1);
    CloseThreadpoolTimer(v20);
    SetLastError(v21);
  }
  *((_QWORD *)this + 15) = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x42,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\usoscheduler\\UsoScheduler.cpp",
      v18);
  UsoScheduler::ResetTimer(this, 1);
  v23[0] = L"Scheduled timer: Name={}";
  v23[1] = 24;
  SystemInterface::Log<std::wstring &>(v23, (char *)this + 128);
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  return this;
}

```

## disassembly

```asm
0x18006f928  mov     [rsp-8+arg_10], rbx
0x18006f92d  push    rbp
0x18006f92e  push    rsi
0x18006f92f  push    rdi
0x18006f930  push    r12
0x18006f932  push    r13
0x18006f934  push    r14
0x18006f936  push    r15
0x18006f938  lea     rbp, [rsp-1Fh]
0x18006f93d  sub     rsp, 90h
0x18006f944  mov     r14b, r9b
0x18006f947  mov     r15, r8
0x18006f94a  mov     rbx, rdx
0x18006f94d  mov     rdi, rcx
0x18006f950  mov     rsi, [rbp+4Fh+arg_20]
0x18006f954  mov     [rbp+4Fh+var_80], rcx
0x18006f958  xor     r8d, r8d; Flags
0x18006f95b  xor     edx, edx; dwSpinCount
0x18006f95d  call    cs:__imp_InitializeCriticalSectionEx
0x18006f963  nop
0x18006f964  xor     r13d, r13d
0x18006f967  mov     [rdi+70h], r13
0x18006f96b  mov     [rdi+78h], r13
0x18006f96f  lea     r12, [rdi+80h]
0x18006f976  mov     rdx, rbx
0x18006f979  mov     rcx, r12
0x18006f97c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006f981  nop
0x18006f982  mov     [rbp+4Fh+var_40], r13
0x18006f986  mov     rcx, [rsi+38h]
0x18006f98a  test    rcx, rcx
0x18006f98d  jz      short loc_18006F9CD
0x18006f98f  cmp     rcx, rsi
0x18006f992  jnz     short loc_18006F9C5
0x18006f994  mov     rax, [rcx]
0x18006f997  lea     rdx, [rbp+4Fh+var_78]
0x18006f99b  mov     rax, [rax+8]
0x18006f99f  call    _guard_dispatch_icall
0x18006f9a4  mov     [rbp+4Fh+var_40], rax
0x18006f9a8  mov     rcx, [rsi+38h]
0x18006f9ac  test    rcx, rcx
0x18006f9af  jz      short loc_18006F9CD
0x18006f9b1  cmp     rcx, rsi
0x18006f9b4  setnz   dl
0x18006f9b7  mov     rax, [rcx]
0x18006f9ba  mov     rax, [rax+20h]
0x18006f9be  call    _guard_dispatch_icall
0x18006f9c3  jmp     short loc_18006F9C9
0x18006f9c5  mov     [rbp+4Fh+var_40], rcx
0x18006f9c9  mov     [rsi+38h], r13
0x18006f9cd  mov     [rdi+110h], r13
0x18006f9d4  lea     rcx, [rdi+0A8h]
0x18006f9db  lea     rdx, [rbp+4Fh+var_78]
0x18006f9df  call    ??0?$__func@V?$function@$$A6AXXZ@std@@$$A6AXXZ@__function@wistd@@QEAA@$$QEAV?$function@$$A6AXXZ@std@@@Z; wistd::__function::__func<std::function<void (void)>,void (void)>::__func<std::function<void (void)>,void (void)>(std::function<void (void)> &&)
0x18006f9e4  mov     [rdi+110h], rax
0x18006f9eb  mov     rcx, [rbp+4Fh+var_40]
0x18006f9ef  test    rcx, rcx
0x18006f9f2  jz      short loc_18006FA0B
0x18006f9f4  lea     rax, [rbp+4Fh+var_78]
0x18006f9f8  cmp     rcx, rax
0x18006f9fb  setnz   dl
0x18006f9fe  mov     rax, [rcx]
0x18006fa01  mov     rax, [rax+20h]
0x18006fa05  call    _guard_dispatch_icall
0x18006fa0a  nop
0x18006fa0b  mov     rax, [r15]
0x18006fa0e  mov     [rdi+118h], rax
0x18006fa15  mov     [rdi+120h], r14b
0x18006fa1c  mov     rcx, rdi; lpCriticalSection
0x18006fa1f  call    cs:__imp_EnterCriticalSection
0x18006fa25  mov     [rbp+4Fh+var_A0], rdi
0x18006fa29  mov     dword ptr [rdi+28h], 3
0x18006fa30  mov     [rdi+30h], r13
0x18006fa34  mov     [rdi+38h], r13
0x18006fa38  mov     [rdi+40h], r13
0x18006fa3c  mov     [rdi+48h], r13
0x18006fa40  mov     [rdi+50h], r13
0x18006fa44  mov     [rdi+58h], r13
0x18006fa48  mov     [rdi+60h], r13d
0x18006fa4c  mov     dword ptr [rdi+64h], 1
0x18006fa53  mov     dword ptr [rdi+68h], 48h ; 'H'
0x18006fa5a  xor     ecx, ecx; reserved
0x18006fa5c  call    cs:__imp_CreateThreadpool
0x18006fa62  mov     r14, rax
0x18006fa65  mov     r15, [rdi+70h]
0x18006fa69  test    r15, r15
0x18006fa6c  jz      short loc_18006FA87
0x18006fa6e  call    cs:__imp_GetLastError
0x18006fa74  mov     ebx, eax
0x18006fa76  mov     rcx, r15; ptpp
0x18006fa79  call    cs:__imp_CloseThreadpool
0x18006fa7f  mov     ecx, ebx; dwErrCode
0x18006fa81  call    cs:__imp_SetLastError
0x18006fa87  mov     [rdi+70h], r14
0x18006fa8b  mov     rcx, [rbp+57h]; this
0x18006fa8f  test    r14, r14
0x18006fa92  jz      loc_18006FB95
0x18006fa98  mov     edx, 1; cthrdMost
0x18006fa9d  mov     rcx, r14; ptpp
0x18006faa0  call    cs:__imp_SetThreadpoolThreadMaximum
0x18006faa6  mov     rbx, [rbp+57h]
0x18006faaa  mov     r15d, 1
0x18006fab0  mov     edx, r15d; cthrdMic
0x18006fab3  mov     rcx, [rdi+70h]; ptpp
0x18006fab7  call    cs:__imp_SetThreadpoolThreadMinimum
0x18006fabd  test    eax, eax
0x18006fabf  jz      loc_18006FBA7
0x18006fac5  mov     rax, [rdi+70h]
0x18006fac9  mov     [rdi+30h], rax
0x18006facd  lea     r8, [rdi+28h]; pcbe
0x18006fad1  mov     rdx, rdi; pv
0x18006fad4  lea     rcx, ?ThreadPoolTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXQEAU_TP_TIMER@@@Z; pfnti
0x18006fadb  call    cs:__imp_CreateThreadpoolTimer
0x18006fae1  mov     r14, rax
0x18006fae4  mov     rsi, [rdi+78h]
0x18006fae8  test    rsi, rsi
0x18006faeb  jz      short loc_18006FB23
0x18006faed  call    cs:__imp_GetLastError
0x18006faf3  mov     ebx, eax
0x18006faf5  xor     r9d, r9d; msWindowLength
0x18006faf8  xor     r8d, r8d; msPeriod
0x18006fafb  xor     edx, edx; pftDueTime
0x18006fafd  mov     rcx, rsi; pti
0x18006fb00  call    cs:__imp_SetThreadpoolTimer
0x18006fb06  mov     edx, r15d; fCancelPendingCallbacks
0x18006fb09  mov     rcx, rsi; pti
0x18006fb0c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006fb12  mov     rcx, rsi; pti
0x18006fb15  call    cs:__imp_CloseThreadpoolTimer
0x18006fb1b  mov     ecx, ebx; dwErrCode
0x18006fb1d  call    cs:__imp_SetLastError
0x18006fb23  mov     [rdi+78h], r14
0x18006fb27  mov     rcx, [rbp+57h]; this
0x18006fb2b  test    r14, r14
0x18006fb2e  jz      short loc_18006FB83
0x18006fb30  mov     dl, r15b; bool
0x18006fb33  mov     rcx, rdi; this
0x18006fb36  call    ?ResetTimer@UsoScheduler@@QEAAX_N@Z; UsoScheduler::ResetTimer(bool)
0x18006fb3b  lea     rax, aScheduledTimer; "Scheduled timer: Name={}"
0x18006fb42  mov     [rbp+4Fh+var_90], rax
0x18006fb46  mov     [rbp+4Fh+var_88], 18h
0x18006fb4e  mov     rdx, r12
0x18006fb51  lea     rcx, [rbp+4Fh+var_90]
0x18006fb55  call    ??$Log@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; SystemInterface::Log<std::wstring &>(std::wstring_view,std::wstring &)
0x18006fb5a  nop
0x18006fb5b  mov     rcx, rdi; lpCriticalSection
0x18006fb5e  call    cs:__imp_LeaveCriticalSection
0x18006fb64  nop
0x18006fb65  mov     rax, rdi
0x18006fb68  mov     rbx, [rsp+0C0h+arg_10]
0x18006fb70  add     rsp, 90h
0x18006fb77  pop     r15
0x18006fb79  pop     r14
0x18006fb7b  pop     r13
0x18006fb7d  pop     r12
0x18006fb7f  pop     rdi
0x18006fb80  pop     rsi
0x18006fb81  pop     rbp
0x18006fb82  retn
0x18006fb83  lea     r8, aCW1SSrcOrchest_26; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18006fb8a  mov     edx, 42h ; 'B'; void *
0x18006fb8f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006fb95  lea     r8, aCW1SSrcOrchest_26; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18006fb9c  mov     edx, 39h ; '9'; void *
0x18006fba1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006fba7  lea     r8, aCW1SSrcOrchest_26; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x18006fbae  mov     edx, 3Dh ; '='; void *
0x18006fbb3  mov     rcx, rbx; this
0x18006fbb6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
