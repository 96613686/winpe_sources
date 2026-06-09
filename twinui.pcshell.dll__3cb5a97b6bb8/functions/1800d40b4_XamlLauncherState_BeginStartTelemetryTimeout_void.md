# XamlLauncherState::BeginStartTelemetryTimeout(void)

- ea: `0x1800d40b4`
- end: `0x1800d4396`
- name: `?BeginStartTelemetryTimeout@XamlLauncherState@@AEAAXXZ`
- size: `738`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1801abe60`

## callees

- `0x1800d40b4`
- `0x1800d44b0`
- `0x1801ab4a8`
- `0x1801f0b58`
- `0x1802de590`
- `0x1802de954`
- `0x1804b0dc0`
- `0x1804b0dd0`
- `0x1804b0de0`
- `0x1804b0e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d418a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d42d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d42f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d430d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d418a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d42d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d42f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d430d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d419c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d42e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d4302`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d431f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d419c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d42e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d4302`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d431f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d40e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d4175`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d41fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d4271`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d40e6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d4175`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d41fd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800d4271`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d4138`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d41e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d4258`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d42c8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d4138`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d41e0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d4258`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800d42c8`

## pseudocode

```c
void __fastcall XamlLauncherState::BeginStartTelemetryTimeout(struct _TP_TIMER **pv)
{
  void (__stdcall *v2)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER); // rax
  PTP_TIMER v3; // rax
  const char *v4; // r9
  struct _TP_TIMER *v5; // rbp
  PTP_TIMER v6; // rsi
  struct _TP_TIMER *v7; // rcx
  unsigned __int64 v8; // rdx
  unsigned __int8 v9; // cl
  void (__stdcall *v10)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER); // rax
  PTP_TIMER v11; // rax
  unsigned __int64 v12; // rdx
  const char *v13; // r9
  struct _TP_TIMER *v14; // rbp
  PTP_TIMER v15; // rsi
  DWORD v16; // ebx
  PTP_TIMER v17; // r10
  void (__stdcall *v18)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER); // rax
  PTP_TIMER v19; // rax
  unsigned __int64 v20; // rdx
  const char *v21; // r9
  struct _TP_TIMER *v22; // rbp
  PTP_TIMER v23; // rsi
  PTP_TIMER v24; // r10
  void (__stdcall *v25)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER); // rax
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned __int64 v27; // rdx
  const char *v28; // r9
  struct _TP_TIMER *v29; // rbp
  PTP_TIMER v30; // rsi
  PTP_TIMER v31; // r10
  DWORD v32; // ebx
  DWORD LastError; // ebx
  DWORD v34; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp+8h] BYREF

  if ( !pv[128] )
  {
    v25 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))lambda_db129b3849abcb1c73d6af2fd2256099_::operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___();
    ThreadpoolTimer = CreateThreadpoolTimer(v25, pv, 0);
    v29 = pv[128];
    v30 = ThreadpoolTimer;
    if ( v29 )
    {
      LastError = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v29);
      SetLastError(LastError);
    }
    pv[128] = v30;
    if ( !v30 )
      wil::details::in1diag3::_Log_NullAlloc(
        retaddr,
        (void *)0x607,
        (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncherstate.cpp",
        v28);
    if ( pv[128] )
    {
      pftDueTime = wil::FileTime::FromInt64((wil::FileTime *)0xFFFFFFFFFECED300LL, v27);
      SetThreadpoolTimer(v31, &pftDueTime, 0, 0x3E8u);
    }
  }
  if ( !pv[129] )
  {
    v2 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))lambda_931ce0dc608757a1e1dcf1ea19462cc3_::operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___();
    v3 = CreateThreadpoolTimer(v2, pv, 0);
    v5 = pv[129];
    v6 = v3;
    if ( v5 )
    {
      v34 = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v5);
      SetLastError(v34);
    }
    pv[129] = v6;
    if ( !v6 )
      wil::details::in1diag3::_Log_NullAlloc(
        retaddr,
        (void *)0x625,
        (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncherstate.cpp",
        v4);
    v7 = pv[129];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)(-10000000LL * *((unsigned int *)pv + 17));
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x3E8u);
      if ( StartWindowTelemetry::IsEnabled(v9, v8) )
        XamlLauncherState::StartTrackingCpuUsageOfCriticalProcesses((XamlLauncherState *)pv);
    }
  }
  if ( !pv[130] )
  {
    v18 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))lambda_08be4a4e2cdf1900e24a8b93e648e3bb_::operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___();
    v19 = CreateThreadpoolTimer(v18, pv, 0);
    v22 = pv[130];
    v23 = v19;
    if ( v22 )
    {
      v32 = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v22);
      SetLastError(v32);
    }
    pv[130] = v23;
    if ( !v23 )
      wil::details::in1diag3::_Log_NullAlloc(
        retaddr,
        (void *)0x640,
        (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncherstate.cpp",
        v21);
    if ( pv[130] )
    {
      pftDueTime = wil::FileTime::FromInt64((wil::FileTime *)0xFFFFFFFFFA0A1F00LL, v20);
      SetThreadpoolTimer(v24, &pftDueTime, 0, 0x3E8u);
    }
  }
  if ( !pv[131] )
  {
    v10 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_TIMER))lambda_92b6c0caea59305e122c6c21e326263b_::operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___();
    v11 = CreateThreadpoolTimer(v10, pv, 0);
    v14 = pv[131];
    v15 = v11;
    if ( v14 )
    {
      v16 = GetLastError();
      wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v14);
      SetLastError(v16);
    }
    pv[131] = v15;
    if ( !v15 )
      wil::details::in1diag3::_Log_NullAlloc(
        retaddr,
        (void *)0x667,
        (unsigned int)"pcshell\\twinui\\xamllauncher\\lib\\xamllauncherstate.cpp",
        v13);
    if ( pv[131] )
    {
      pftDueTime = wil::FileTime::FromInt64((wil::FileTime *)0xFFFFFFFFEE1E5D00LL, v12);
      SetThreadpoolTimer(v17, &pftDueTime, 0, 0x3E8u);
    }
  }
}

```

## disassembly

```asm
0x1800d40b4  push    rbx
0x1800d40b6  push    rbp
0x1800d40b7  push    rsi
0x1800d40b8  push    rdi
0x1800d40b9  sub     rsp, 28h
0x1800d40bd  cmp     qword ptr [rcx+400h], 0
0x1800d40c5  mov     rdi, rcx
0x1800d40c8  jz      loc_1800D4263
0x1800d40ce  cmp     qword ptr [rdi+408h], 0
0x1800d40d6  jnz     short loc_1800D414F
0x1800d40d8  call    _lambda_931ce0dc608757a1e1dcf1ea19462cc3___operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___
0x1800d40dd  mov     rcx, rax; pfnti
0x1800d40e0  xor     r8d, r8d; pcbe
0x1800d40e3  mov     rdx, rdi; pv
0x1800d40e6  call    cs:__imp_CreateThreadpoolTimer
0x1800d40ec  mov     rbp, [rdi+408h]
0x1800d40f3  mov     rsi, rax
0x1800d40f6  test    rbp, rbp
0x1800d40f9  jnz     loc_1800D430D
0x1800d40ff  mov     [rdi+408h], rsi
0x1800d4106  test    rsi, rsi
0x1800d4109  jz      loc_1800D4345
0x1800d410f  mov     rcx, [rdi+408h]; pti
0x1800d4116  test    rcx, rcx
0x1800d4119  jz      short loc_1800D414F
0x1800d411b  mov     eax, [rdi+44h]
0x1800d411e  mov     r9d, 3E8h; msWindowLength
0x1800d4124  imul    rdx, rax, 0FFFFFFFFFF676980h
0x1800d412b  xor     r8d, r8d; msPeriod
0x1800d412e  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x1800d4133  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800d4138  call    cs:__imp_SetThreadpoolTimer
0x1800d413e  call    ?IsEnabled@StartWindowTelemetry@@SA_NE_K@Z; StartWindowTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800d4143  test    al, al
0x1800d4145  jz      short loc_1800D414F
0x1800d4147  mov     rcx, rdi; this
0x1800d414a  call    ?StartTrackingCpuUsageOfCriticalProcesses@XamlLauncherState@@AEAAXXZ; XamlLauncherState::StartTrackingCpuUsageOfCriticalProcesses(void)
0x1800d414f  cmp     qword ptr [rdi+410h], 0
0x1800d4157  jz      loc_1800D41EF
0x1800d415d  cmp     qword ptr [rdi+418h], 0
0x1800d4165  jnz     short loc_1800D41E6
0x1800d4167  call    _lambda_92b6c0caea59305e122c6c21e326263b___operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___
0x1800d416c  mov     rcx, rax; pfnti
0x1800d416f  xor     r8d, r8d; pcbe
0x1800d4172  mov     rdx, rdi; pv
0x1800d4175  call    cs:__imp_CreateThreadpoolTimer
0x1800d417b  mov     rbp, [rdi+418h]
0x1800d4182  mov     rsi, rax
0x1800d4185  test    rbp, rbp
0x1800d4188  jz      short loc_1800D41A2
0x1800d418a  call    cs:__imp_GetLastError
0x1800d4190  mov     rcx, rbp; pti
0x1800d4193  mov     ebx, eax
0x1800d4195  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800d419a  mov     ecx, ebx; dwErrCode
0x1800d419c  call    cs:__imp_SetLastError
0x1800d41a2  mov     [rdi+418h], rsi
0x1800d41a9  test    rsi, rsi
0x1800d41ac  jz      loc_1800D437B
0x1800d41b2  mov     r10, [rdi+418h]
0x1800d41b9  test    r10, r10
0x1800d41bc  jz      short loc_1800D41E6
0x1800d41be  mov     rcx, 0FFFFFFFFEE1E5D00h; this
0x1800d41c5  call    ?FromInt64@FileTime@wil@@YA?AU_FILETIME@@_K@Z; wil::FileTime::FromInt64(unsigned __int64)
0x1800d41ca  mov     r9d, 3E8h; msWindowLength
0x1800d41d0  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800d41d5  xor     r8d, r8d; msPeriod
0x1800d41d8  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800d41dd  mov     rcx, r10; pti
0x1800d41e0  call    cs:__imp_SetThreadpoolTimer
0x1800d41e6  add     rsp, 28h
0x1800d41ea  pop     rdi
0x1800d41eb  pop     rsi
0x1800d41ec  pop     rbp
0x1800d41ed  pop     rbx
0x1800d41ee  retn
0x1800d41ef  call    _lambda_08be4a4e2cdf1900e24a8b93e648e3bb___operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___
0x1800d41f4  mov     rcx, rax; pfnti
0x1800d41f7  xor     r8d, r8d; pcbe
0x1800d41fa  mov     rdx, rdi; pv
0x1800d41fd  call    cs:__imp_CreateThreadpoolTimer
0x1800d4203  mov     rbp, [rdi+410h]
0x1800d420a  mov     rsi, rax
0x1800d420d  test    rbp, rbp
0x1800d4210  jnz     loc_1800D42D3
0x1800d4216  mov     [rdi+410h], rsi
0x1800d421d  test    rsi, rsi
0x1800d4220  jz      loc_1800D4360
0x1800d4226  mov     r10, [rdi+410h]
0x1800d422d  test    r10, r10
0x1800d4230  jz      loc_1800D415D
0x1800d4236  mov     rcx, 0FFFFFFFFFA0A1F00h; this
0x1800d423d  call    ?FromInt64@FileTime@wil@@YA?AU_FILETIME@@_K@Z; wil::FileTime::FromInt64(unsigned __int64)
0x1800d4242  mov     r9d, 3E8h; msWindowLength
0x1800d4248  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800d424d  xor     r8d, r8d; msPeriod
0x1800d4250  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800d4255  mov     rcx, r10; pti
0x1800d4258  call    cs:__imp_SetThreadpoolTimer
0x1800d425e  jmp     loc_1800D415D
0x1800d4263  call    _lambda_db129b3849abcb1c73d6af2fd2256099___operator_void____cdecl____TP_CALLBACK_INSTANCE___void____TP_TIMER___
0x1800d4268  mov     rcx, rax; pfnti
0x1800d426b  xor     r8d, r8d; pcbe
0x1800d426e  mov     rdx, rdi; pv
0x1800d4271  call    cs:__imp_CreateThreadpoolTimer
0x1800d4277  mov     rbp, [rdi+400h]
0x1800d427e  mov     rsi, rax
0x1800d4281  test    rbp, rbp
0x1800d4284  jnz     short loc_1800D42F0
0x1800d4286  mov     [rdi+400h], rsi
0x1800d428d  test    rsi, rsi
0x1800d4290  jz      loc_1800D432A
0x1800d4296  mov     r10, [rdi+400h]
0x1800d429d  test    r10, r10
0x1800d42a0  jz      loc_1800D40CE
0x1800d42a6  mov     rcx, 0FFFFFFFFFECED300h; this
0x1800d42ad  call    ?FromInt64@FileTime@wil@@YA?AU_FILETIME@@_K@Z; wil::FileTime::FromInt64(unsigned __int64)
0x1800d42b2  mov     r9d, 3E8h; msWindowLength
0x1800d42b8  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800d42bd  xor     r8d, r8d; msPeriod
0x1800d42c0  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800d42c5  mov     rcx, r10; pti
0x1800d42c8  call    cs:__imp_SetThreadpoolTimer
0x1800d42ce  jmp     loc_1800D40CE
0x1800d42d3  call    cs:__imp_GetLastError
0x1800d42d9  mov     rcx, rbp; pti
0x1800d42dc  mov     ebx, eax
0x1800d42de  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800d42e3  mov     ecx, ebx; dwErrCode
0x1800d42e5  call    cs:__imp_SetLastError
0x1800d42eb  jmp     loc_1800D4216
0x1800d42f0  call    cs:__imp_GetLastError
0x1800d42f6  mov     rcx, rbp; pti
0x1800d42f9  mov     ebx, eax
0x1800d42fb  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800d4300  mov     ecx, ebx; dwErrCode
0x1800d4302  call    cs:__imp_SetLastError
0x1800d4308  jmp     loc_1800D4286
0x1800d430d  call    cs:__imp_GetLastError
0x1800d4313  mov     rcx, rbp; pti
0x1800d4316  mov     ebx, eax
0x1800d4318  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1800d431d  mov     ecx, ebx; dwErrCode
0x1800d431f  call    cs:__imp_SetLastError
0x1800d4325  jmp     loc_1800D40FF
0x1800d432a  mov     rcx, [rsp+48h]; this
0x1800d432f  lea     r8, aPcshellTwinuiX_0; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x1800d4336  mov     edx, 607h; void *
0x1800d433b  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x1800d4340  jmp     loc_1800D4296
0x1800d4345  mov     rcx, [rsp+48h]; this
0x1800d434a  lea     r8, aPcshellTwinuiX_0; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x1800d4351  mov     edx, 625h; void *
0x1800d4356  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x1800d435b  jmp     loc_1800D410F
0x1800d4360  mov     rcx, [rsp+48h]; this
0x1800d4365  lea     r8, aPcshellTwinuiX_0; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x1800d436c  mov     edx, 640h; void *
0x1800d4371  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x1800d4376  jmp     loc_1800D4226
0x1800d437b  mov     rcx, [rsp+48h]; this
0x1800d4380  lea     r8, aPcshellTwinuiX_0; "pcshell\\twinui\\xamllauncher\\lib\\xam"...
0x1800d4387  mov     edx, 667h; void *
0x1800d438c  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x1800d4391  jmp     loc_1800D41B2
```
