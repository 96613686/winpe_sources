# CThemeManagerDispatcher::CreateAndQueueRequest(CPortMessage const &)

- ea: `0x180004d80`
- end: `0x1800050b0`
- name: `?CreateAndQueueRequest@CThemeManagerDispatcher@@UEAAJAEBVCPortMessage@@@Z`
- size: `816`
- prototype: `__int64 __fastcall(CThemeManagerDispatcher *__hidden this, const struct CPortMessage *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180003f90`
- `0x180004084`
- `0x180004d80`
- `0x18000674c`
- `0x1800067e0`
- `0x18000eb30`
- `0x18000fa00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004e8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f24`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004e6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e95`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004f8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004f8d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004ecb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004ecb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004efd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004f72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004efd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004f72`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004f82`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004f82`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004dab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004dab`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180004fc9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180004fc9`

## pseudocode

```c
__int64 __fastcall CThemeManagerDispatcher::CreateAndQueueRequest(
        CThemeManagerDispatcher *this,
        const struct CPortMessage *a2)
{
  char *v4; // rdi
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  unsigned int Error; // edi
  _QWORD *v11; // rcx
  signed int LastError; // eax
  bool v13; // sf
  DWORD pv; // [rsp+30h] [rbp-48h] BYREF
  PTP_TIMER pti; // [rsp+38h] [rbp-40h]
  int v16; // [rsp+40h] [rbp-38h]
  __int64 (__fastcall *v17)(); // [rsp+48h] [rbp-30h]
  int v18; // [rsp+50h] [rbp-28h]
  _FILETIME pftDueTime; // [rsp+58h] [rbp-20h] BYREF

  v4 = (char *)LocalAlloc(0, 0xA0u);
  if ( !v4 )
    return 3221225495LL;
  *(_QWORD *)v4 = &CQueueElement::`vftable';
  *((_QWORD *)v4 + 1) = 0;
  *((_QWORD *)v4 + 2) = &CPortMessage::`vftable';
  *(_OWORD *)(v4 + 24) = *(_OWORD *)((char *)a2 + 8);
  *(_OWORD *)(v4 + 40) = *(_OWORD *)((char *)a2 + 24);
  *(_OWORD *)(v4 + 56) = *(_OWORD *)((char *)a2 + 40);
  *(_OWORD *)(v4 + 72) = *(_OWORD *)((char *)a2 + 56);
  *(_OWORD *)(v4 + 88) = *(_OWORD *)((char *)a2 + 72);
  *(_OWORD *)(v4 + 104) = *(_OWORD *)((char *)a2 + 88);
  *(_OWORD *)(v4 + 120) = *(_OWORD *)((char *)a2 + 104);
  if ( *((_WORD *)v4 + 13) > 0x70u )
    *((_DWORD *)v4 + 6) = 2621440;
  *((_QWORD *)v4 + 17) = this;
  *(_QWORD *)v4 = &CAPIRequest::`vftable'{for `CQueueElement'};
  *((_QWORD *)v4 + 2) = &CAPIRequest::`vftable'{for `CPortMessage'};
  _InterlockedIncrement((volatile signed __int32 *)this + 2);
  *((_QWORD *)v4 + 18) = 0;
  *(_QWORD *)v4 = &CThemeManagerAPIRequest::`vftable'{for `CQueueElement'};
  *((_QWORD *)v4 + 2) = &CThemeManagerAPIRequest::`vftable'{for `CPortMessage'};
  *((_QWORD *)v4 + 19) = 0;
  if ( *((int *)this + 10) >= 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v5 = *((_QWORD *)this + 4);
  if ( v5 )
  {
    do
    {
      v11 = (_QWORD *)(v5 + 8);
      v5 = *(_QWORD *)(v5 + 8);
    }
    while ( v5 );
    *v11 = v4;
  }
  else
  {
    *((_QWORD *)this + 4) = v4;
  }
  if ( *((int *)this + 10) >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  pti = 0;
  pv = GetCurrentThreadId();
  v18 = 0;
  v17 = lambda_5f770da2dd2c1eaf728207a2133e565c_::_lambda_invoker_cdecl_;
  v16 = 5000;
  pti = CreateThreadpoolTimer(ExecutionWatchDogTimer::OnTimeoutReached, &pv, 0);
  if ( pti )
  {
    pftDueTime = (_FILETIME)-(__int64)(unsigned int)(10000 * v16);
    SetThreadpoolTimer(pti, &pftDueTime, 0, 0);
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError < 0;
    if ( LastError > 0 )
      v13 = 1;
    if ( v13 )
    {
      v17 = 0;
      v16 = 0;
      pti = 0;
      v18 = 0;
      goto LABEL_13;
    }
  }
  v18 = 1;
LABEL_13:
  if ( (Microsoft_Windows_UxThemeEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v7, ShellTraceId_ThemeService_SignalRequestPending_Start, v8, 1, &pftDueTime);
  if ( *((int *)this + 30) >= 0 )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  if ( *((_BYTE *)this + 112) )
  {
    Error = 0;
  }
  else
  {
    *((_BYTE *)this + 112) = 1;
    _InterlockedIncrement((volatile signed __int32 *)this + 2);
    if ( QueueUserWorkItem(CWorkItem::WorkItemEntryProc, this, 0) )
    {
      Error = 0;
    }
    else
    {
      CCountedObject::Release(this);
      Error = CStatusCode::StatusCodeOfLastError();
    }
    if ( (Microsoft_Windows_UxThemeEnableBits & 1) != 0 )
      McTemplateU0t_EventWriteTransfer(v7, "\"", Error);
  }
  if ( (Microsoft_Windows_UxThemeEnableBits & 1) != 0 )
    McTemplateU0tq_EventWriteTransfer(v7, v6, *((unsigned __int8 *)this + 112), Error);
  if ( *((int *)this + 30) >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  if ( v18 )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(pti, 1);
    CloseThreadpoolTimer(pti);
  }
  return Error;
}

```

## disassembly

```asm
0x180004d80  mov     [rsp+arg_10], rbx
0x180004d85  mov     [rsp+arg_18], rsi
0x180004d8a  push    rdi
0x180004d8b  sub     rsp, 70h
0x180004d8f  mov     rax, cs:__security_cookie
0x180004d96  xor     rax, rsp
0x180004d99  mov     [rsp+78h+var_10], rax
0x180004d9e  mov     rsi, rdx
0x180004da1  mov     rbx, rcx
0x180004da4  mov     edx, 0A0h; uBytes
0x180004da9  xor     ecx, ecx; uFlags
0x180004dab  call    cs:__imp_LocalAlloc
0x180004db1  mov     rdi, rax
0x180004db4  test    rax, rax
0x180004db7  jz      loc_180005020
0x180004dbd  lea     rax, ??_7CQueueElement@@6B@; const CQueueElement::`vftable'
0x180004dc4  mov     [rsp+78h+arg_8], rbp
0x180004dcc  mov     [rdi], rax
0x180004dcf  xor     ebp, ebp
0x180004dd1  mov     [rdi+8], rbp
0x180004dd5  lea     rax, ??_7CPortMessage@@6B@; const CPortMessage::`vftable'
0x180004ddc  mov     [rdi+10h], rax
0x180004de0  movups  xmm0, xmmword ptr [rsi+8]
0x180004de4  movups  xmmword ptr [rdi+18h], xmm0
0x180004de8  movups  xmm1, xmmword ptr [rsi+18h]
0x180004dec  movups  xmmword ptr [rdi+28h], xmm1
0x180004df0  movups  xmm0, xmmword ptr [rsi+28h]
0x180004df4  movups  xmmword ptr [rdi+38h], xmm0
0x180004df8  movups  xmm1, xmmword ptr [rsi+38h]
0x180004dfc  movups  xmmword ptr [rdi+48h], xmm1
0x180004e00  movups  xmm0, xmmword ptr [rsi+48h]
0x180004e04  movups  xmmword ptr [rdi+58h], xmm0
0x180004e08  movups  xmm1, xmmword ptr [rsi+58h]
0x180004e0c  movups  xmmword ptr [rdi+68h], xmm1
0x180004e10  movups  xmm0, xmmword ptr [rsi+68h]
0x180004e14  movups  xmmword ptr [rdi+78h], xmm0
0x180004e18  cmp     word ptr [rdi+1Ah], 70h ; 'p'
0x180004e1d  ja      loc_180005065
0x180004e23  lea     rax, ??_7CAPIRequest@@6BCQueueElement@@@; const CAPIRequest::`vftable'{for `CQueueElement'}
0x180004e2a  mov     [rdi+88h], rbx
0x180004e31  mov     [rdi], rax
0x180004e34  lea     rax, ??_7CAPIRequest@@6BCPortMessage@@@; const CAPIRequest::`vftable'{for `CPortMessage'}
0x180004e3b  mov     [rdi+10h], rax
0x180004e3f  lock inc dword ptr [rbx+8]
0x180004e43  lea     rax, ??_7CThemeManagerAPIRequest@@6BCQueueElement@@@; const CThemeManagerAPIRequest::`vftable'{for `CQueueElement'}
0x180004e4a  mov     [rdi+90h], rbp
0x180004e51  mov     [rdi], rax
0x180004e54  lea     rax, ??_7CThemeManagerAPIRequest@@6BCPortMessage@@@; const CThemeManagerAPIRequest::`vftable'{for `CPortMessage'}
0x180004e5b  mov     [rdi+10h], rax
0x180004e5f  mov     [rdi+98h], rbp
0x180004e66  cmp     [rbx+28h], ebp
0x180004e69  jl      short loc_180004E75
0x180004e6b  lea     rcx, [rbx+30h]; lpCriticalSection
0x180004e6f  call    cs:__imp_EnterCriticalSection
0x180004e75  mov     rax, [rbx+20h]
0x180004e79  test    rax, rax
0x180004e7c  jnz     loc_180005000
0x180004e82  mov     [rbx+20h], rdi
0x180004e86  cmp     [rbx+28h], ebp
0x180004e89  jl      short loc_180004E95
0x180004e8b  lea     rcx, [rbx+30h]; lpCriticalSection
0x180004e8f  call    cs:__imp_LeaveCriticalSection
0x180004e95  call    cs:__imp_GetCurrentThreadId
0x180004e9b  xor     r8d, r8d; pcbe
0x180004e9e  mov     [rsp+78h+pti], rbp
0x180004ea3  mov     [rsp+78h+pv], eax
0x180004ea7  lea     rdx, [rsp+78h+pv]; pv
0x180004eac  lea     rax, _lambda_5f770da2dd2c1eaf728207a2133e565c____lambda_invoker_cdecl_
0x180004eb3  mov     [rsp+78h+var_28], ebp
0x180004eb7  lea     rcx, ?OnTimeoutReached@ExecutionWatchDogTimer@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004ebe  mov     [rsp+78h+var_30], rax
0x180004ec3  mov     [rsp+78h+var_38], 1388h
0x180004ecb  call    cs:__imp_CreateThreadpoolTimer
0x180004ed1  mov     [rsp+78h+pti], rax
0x180004ed6  mov     rcx, rax; pti
0x180004ed9  test    rax, rax
0x180004edc  jz      loc_18000502A
0x180004ee2  imul    edx, [rsp+78h+var_38], 2710h
0x180004eea  xor     r9d, r9d; msWindowLength
0x180004eed  xor     r8d, r8d; msPeriod
0x180004ef0  neg     rdx
0x180004ef3  mov     qword ptr [rsp+78h+pftDueTime.dwLowDateTime], rdx
0x180004ef8  lea     rdx, [rsp+78h+pftDueTime]; pftDueTime
0x180004efd  call    cs:__imp_SetThreadpoolTimer
0x180004f03  mov     [rsp+78h+var_28], 1
0x180004f0b  test    byte ptr cs:Microsoft_Windows_UxThemeEnableBits, 1
0x180004f12  jnz     loc_18000507D
0x180004f18  cmp     [rbx+78h], ebp
0x180004f1b  jl      short loc_180004F2A
0x180004f1d  lea     rcx, [rbx+80h]; lpCriticalSection
0x180004f24  call    cs:__imp_EnterCriticalSection
0x180004f2a  cmp     [rbx+70h], bpl
0x180004f2e  jz      loc_180004FB4
0x180004f34  mov     edi, ebp
0x180004f36  test    byte ptr cs:Microsoft_Windows_UxThemeEnableBits, 1
0x180004f3d  mov     rbp, [rsp+78h+arg_8]
0x180004f45  jnz     loc_18000509E
0x180004f4b  cmp     dword ptr [rbx+78h], 0
0x180004f4f  jl      short loc_180004F5E
0x180004f51  lea     rcx, [rbx+80h]; lpCriticalSection
0x180004f58  call    cs:__imp_LeaveCriticalSection
0x180004f5e  cmp     [rsp+78h+var_28], 0
0x180004f63  jz      short loc_180004F93
0x180004f65  mov     rcx, [rsp+78h+pti]; pti
0x180004f6a  xor     r9d, r9d; msWindowLength
0x180004f6d  xor     r8d, r8d; msPeriod
0x180004f70  xor     edx, edx; pftDueTime
0x180004f72  call    cs:__imp_SetThreadpoolTimer
0x180004f78  mov     rcx, [rsp+78h+pti]; pti
0x180004f7d  mov     edx, 1; fCancelPendingCallbacks
0x180004f82  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004f88  mov     rcx, [rsp+78h+pti]; pti
0x180004f8d  call    cs:__imp_CloseThreadpoolTimer
0x180004f93  mov     eax, edi
0x180004f95  mov     rcx, [rsp+78h+var_10]
0x180004f9a  xor     rcx, rsp; StackCookie
0x180004f9d  call    __security_check_cookie
0x180004fa2  lea     r11, [rsp+78h+var_8]
0x180004fa7  mov     rbx, [r11+20h]
0x180004fab  mov     rsi, [r11+28h]
0x180004faf  mov     rsp, r11
0x180004fb2  pop     rdi
0x180004fb3  retn
0x180004fb4  mov     byte ptr [rbx+70h], 1
0x180004fb8  lock inc dword ptr [rbx+8]
0x180004fbc  xor     r8d, r8d; Flags
0x180004fbf  lea     rcx, ?WorkItemEntryProc@CWorkItem@@CAKPEAX@Z; Function
0x180004fc6  mov     rdx, rbx; Context
0x180004fc9  call    cs:__imp_QueueUserWorkItem
0x180004fcf  test    eax, eax
0x180004fd1  jz      loc_180005051
0x180004fd7  mov     edi, ebp
0x180004fd9  test    byte ptr cs:Microsoft_Windows_UxThemeEnableBits, 1
0x180004fe0  jz      loc_180004F36
0x180004fe6  mov     r8d, edi
0x180004fe9  lea     rdx, ShellTraceId_ThemeService_QueuingThreadpoolWorker; "\""
0x180004ff0  call    McTemplateU0t_EventWriteTransfer
0x180004ff5  jmp     loc_180004F36
0x180005000  lea     rcx, [rax+8]
0x180005004  mov     rdx, rax
0x180005007  mov     rax, [rcx]
0x18000500a  test    rax, rax
0x18000500d  jnz     short loc_180005000
0x18000500f  test    rdx, rdx
0x180005012  jz      loc_180004E82
0x180005018  mov     [rcx], rdi
0x18000501b  jmp     loc_180004E86
0x180005020  mov     eax, 0C0000017h
0x180005025  jmp     loc_180004F95
0x18000502a  call    cs:__imp_GetLastError
0x180005030  test    eax, eax
0x180005032  jg      short loc_180005071
0x180005034  jns     loc_180004F03
0x18000503a  mov     [rsp+78h+var_30], rbp
0x18000503f  mov     [rsp+78h+var_38], ebp
0x180005043  mov     [rsp+78h+pti], rbp
0x180005048  mov     [rsp+78h+var_28], ebp
0x18000504c  jmp     loc_180004F0B
0x180005051  mov     rcx, rbx; this
0x180005054  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x180005059  call    ?StatusCodeOfLastError@CStatusCode@@SAJXZ; CStatusCode::StatusCodeOfLastError(void)
0x18000505e  mov     edi, eax
0x180005060  jmp     loc_180004FD9
0x180005065  mov     dword ptr [rdi+18h], 280000h
0x18000506c  jmp     loc_180004E23
0x180005071  movzx   eax, ax
0x180005074  or      eax, 80070000h
0x180005079  test    eax, eax
0x18000507b  jmp     short loc_180005034
0x18000507d  lea     rax, [rsp+78h+pftDueTime]
0x180005082  mov     r9d, 1
0x180005088  lea     rdx, ShellTraceId_ThemeService_SignalRequestPending_Start
0x18000508f  mov     [rsp+78h+var_58], rax
0x180005094  call    McGenEventWrite_EventWriteTransfer
0x180005099  jmp     loc_180004F18
0x18000509e  movzx   r8d, byte ptr [rbx+70h]
0x1800050a3  mov     r9d, edi
0x1800050a6  call    McTemplateU0tq_EventWriteTransfer
0x1800050ab  jmp     loc_180004F4B
```
