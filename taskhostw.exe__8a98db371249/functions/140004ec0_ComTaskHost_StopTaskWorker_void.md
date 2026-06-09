# ComTaskHost::StopTaskWorker(void)

- ea: `0x140004ec0`
- end: `0x1400050b9`
- name: `?StopTaskWorker@ComTaskHost@@AEAAJXZ`
- size: `505`
- prototype: `__int64 __fastcall(ComTaskHost *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140007330`
- `0x140007360`

## callees

- `0x140004ec0`
- `0x1400050c0`
- `0x140005150`
- `0x140005270`
- `0x140009370`
- `0x140009be0`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004f6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004f09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140004f6f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140004f12`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140004f12`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004f30`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004f7a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004f30`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140004f7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004ffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005077`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004ffc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140005077`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000504c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000504c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x140004fe5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x140004fe5`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140004fed`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140004fed`

## string_xrefs

- `0x140004f93`: `StopTaskWorker`

## pseudocode

```c
__int64 __fastcall ComTaskHost::StopTaskWorker(ComTaskHost *this)
{
  int started; // edi
  int v3; // edi
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE v6; // rax
  signed __int64 v7; // r8
  HANDLE v8; // rax
  signed __int64 v9; // r8
  HANDLE Timer; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+68h] [rbp+10h] BYREF
  int v13; // [rsp+70h] [rbp+18h]

  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this);
  started = ComTaskHost::WaitForTaskStartCompletion(this);
  if ( started >= 0 )
  {
    v3 = *((_DWORD *)this + 16);
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    v13 = ThreadPriority;
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v6 = GetCurrentThread();
      if ( !SetThreadPriority(v6, v3) )
      {
        ThreadPriority = 0x7FFFFFFF;
        v13 = 0x7FFFFFFF;
      }
    }
    if ( *((_BYTE *)this + 48) )
    {
      v7 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, 0, 0);
      started = (*(__int64 (__fastcall **)(signed __int64, int *))(*(_QWORD *)v7 + 32LL))(v7, &v12);
    }
    else
    {
      ComCallAutoCancel::ComCallAutoCancel(&Timer);
      v9 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 9, 0, 0);
      started = (*(__int64 (__fastcall **)(signed __int64, int *))(*(_QWORD *)v9 + 32LL))(v9, &v12);
      if ( Timer )
      {
        DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
        CoDisableCallCancellation(0);
      }
    }
    if ( ThreadPriority != 0x7FFFFFFF )
    {
      v8 = GetCurrentThread();
      SetThreadPriority(v8, ThreadPriority);
    }
    if ( started >= 0 )
      started = v12;
  }
  if ( started != -2147009395 )
    goto LABEL_15;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  if ( *((_DWORD *)this + 22) )
  {
    started = *((_DWORD *)this + 23);
    goto LABEL_18;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 8) == 8 )
  {
LABEL_18:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    if ( started == -2147009395 )
      goto LABEL_19;
    goto LABEL_15;
  }
  started = -2147418113;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
LABEL_15:
  ComTaskHost::ReleaseLifetimeRef(this, L"StopTaskWorker");
LABEL_19:
  if ( started < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids, this, started);
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x140004ec0  mov     [rsp+arg_0], rbx
0x140004ec5  push    rbp
0x140004ec6  push    rsi
0x140004ec7  push    rdi
0x140004ec8  sub     rsp, 40h
0x140004ecc  mov     rsi, rcx
0x140004ecf  mov     [rsp+58h+arg_8], 0
0x140004ed7  lea     rbp, WPP_GLOBAL_Control
0x140004ede  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ee5  cmp     rcx, rbp
0x140004ee8  jz      short loc_140004EF4
0x140004eea  test    byte ptr [rcx+1Ch], 4
0x140004eee  jnz     loc_14000501D
0x140004ef4  mov     rcx, rsi; this
0x140004ef7  call    ?WaitForTaskStartCompletion@ComTaskHost@@AEAAJXZ; ComTaskHost::WaitForTaskStartCompletion(void)
0x140004efc  mov     edi, eax
0x140004efe  test    eax, eax
0x140004f00  js      loc_140004F87
0x140004f06  mov     edi, [rsi+40h]
0x140004f09  call    cs:__imp_GetCurrentThread
0x140004f0f  mov     rcx, rax; hThread
0x140004f12  call    cs:__imp_GetThreadPriority
0x140004f18  mov     ebx, eax
0x140004f1a  mov     [rsp+58h+arg_10], eax
0x140004f1e  cmp     eax, 7FFFFFFFh
0x140004f23  jz      short loc_140004F3E
0x140004f25  call    cs:__imp_GetCurrentThread
0x140004f2b  mov     rcx, rax; hThread
0x140004f2e  mov     edx, edi; nPriority
0x140004f30  call    cs:__imp_SetThreadPriority
0x140004f36  test    eax, eax
0x140004f38  jz      loc_14000503A
0x140004f3e  cmp     byte ptr [rsi+30h], 0
0x140004f42  jz      short loc_140004FA4
0x140004f44  xor     ecx, ecx
0x140004f46  xor     eax, eax
0x140004f48  lock cmpxchg [rsi+48h], rcx
0x140004f4e  mov     r8, rax
0x140004f51  mov     rcx, [rax]
0x140004f54  mov     rax, [rcx+20h]
0x140004f58  lea     rdx, [rsp+58h+arg_8]
0x140004f5d  mov     rcx, r8
0x140004f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f65  mov     edi, eax
0x140004f67  cmp     ebx, 7FFFFFFFh
0x140004f6d  jz      short loc_140004F80
0x140004f6f  call    cs:__imp_GetCurrentThread
0x140004f75  mov     edx, ebx; nPriority
0x140004f77  mov     rcx, rax; hThread
0x140004f7a  call    cs:__imp_SetThreadPriority
0x140004f80  test    edi, edi
0x140004f82  cmovns  edi, [rsp+58h+arg_8]
0x140004f87  cmp     edi, 80073C8Dh
0x140004f8d  jz      loc_140005048
0x140004f93  lea     rdx, aStoptaskworker; "StopTaskWorker"
0x140004f9a  mov     rcx, rsi; this
0x140004f9d  call    ?ReleaseLifetimeRef@ComTaskHost@@QEAAKPEBG@Z; ComTaskHost::ReleaseLifetimeRef(ushort const *)
0x140004fa2  jmp     short loc_14000500A
0x140004fa4  lea     rcx, [rsp+58h+Timer]; Parameter
0x140004fa9  call    ??0ComCallAutoCancel@@QEAA@XZ; ComCallAutoCancel::ComCallAutoCancel(void)
0x140004fae  nop
0x140004faf  xor     ecx, ecx
0x140004fb1  xor     eax, eax
0x140004fb3  lock cmpxchg [rsi+48h], rcx
0x140004fb9  mov     r8, rax
0x140004fbc  mov     rcx, [rax]
0x140004fbf  mov     rax, [rcx+20h]
0x140004fc3  lea     rdx, [rsp+58h+arg_8]
0x140004fc8  mov     rcx, r8
0x140004fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fd0  mov     edi, eax
0x140004fd2  mov     rdx, [rsp+58h+Timer]; Timer
0x140004fd7  test    rdx, rdx
0x140004fda  jz      short loc_140004F67
0x140004fdc  xor     ecx, ecx; TimerQueue
0x140004fde  mov     r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140004fe5  call    cs:__imp_DeleteTimerQueueTimer
0x140004feb  xor     ecx, ecx; pReserved
0x140004fed  call    cs:__imp_CoDisableCallCancellation
0x140004ff3  jmp     loc_140004F67
0x140004ff8  lea     rcx, [rsi+60h]; lpCriticalSection
0x140004ffc  call    cs:__imp_LeaveCriticalSection
0x140005002  cmp     edi, 80073C8Dh
0x140005008  jnz     short loc_140004F93
0x14000500a  test    edi, edi
0x14000500c  js      short loc_140005082
0x14000500e  mov     eax, edi
0x140005010  mov     rbx, [rsp+58h+arg_0]
0x140005015  add     rsp, 40h
0x140005019  pop     rdi
0x14000501a  pop     rsi
0x14000501b  pop     rbp
0x14000501c  retn
0x14000501d  mov     edx, 13h
0x140005022  mov     r9, rsi
0x140005025  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x14000502c  mov     rcx, [rcx+10h]
0x140005030  call    WPP_SF_q
0x140005035  jmp     loc_140004EF4
0x14000503a  mov     ebx, 7FFFFFFFh
0x14000503f  mov     [rsp+58h+arg_10], ebx
0x140005043  jmp     loc_140004F3E
0x140005048  lea     rcx, [rsi+60h]; lpCriticalSection
0x14000504c  call    cs:__imp_EnterCriticalSection
0x140005052  cmp     dword ptr [rsi+58h], 0
0x140005056  jz      short loc_14000505D
0x140005058  mov     edi, [rsi+5Ch]
0x14000505b  jmp     short loc_140004FF8
0x14000505d  mov     ecx, 1
0x140005062  mov     eax, 8
0x140005067  lock cmpxchg [rsi+10h], ecx
0x14000506c  jz      short loc_140004FF8
0x14000506e  mov     edi, 8000FFFFh
0x140005073  lea     rcx, [rsi+60h]; lpCriticalSection
0x140005077  call    cs:__imp_LeaveCriticalSection
0x14000507d  jmp     loc_140004F93
0x140005082  mov     rcx, cs:WPP_GLOBAL_Control
0x140005089  cmp     rcx, rbp
0x14000508c  jz      short loc_14000500E
0x14000508e  test    byte ptr [rcx+1Ch], 1
0x140005092  jz      loc_14000500E
0x140005098  mov     edx, 14h
0x14000509d  mov     [rsp+58h+var_38], edi
0x1400050a1  mov     r9, rsi
0x1400050a4  lea     r8, WPP_1a6c4c03277a3f60c8ecdbf3dacca60d_Traceguids
0x1400050ab  mov     rcx, [rcx+10h]
0x1400050af  call    WPP_SF_qD
0x1400050b4  jmp     loc_14000500E
```
