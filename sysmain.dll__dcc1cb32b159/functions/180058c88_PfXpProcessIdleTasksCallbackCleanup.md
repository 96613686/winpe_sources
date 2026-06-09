# PfXpProcessIdleTasksCallbackCleanup

- ea: `0x180058c88`
- end: `0x180058d52`
- name: `PfXpProcessIdleTasksCallbackCleanup`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x180058978`
- `0x180058b30`

## callees

- `0x180058c88`
- `0x180058d58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058c9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058d31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058c9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058d31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058caf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058caf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058d4b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180058ce5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180058ce5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180058cd8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180058cd8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058cc6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058cc6`

## pseudocode

```c
void __fastcall PfXpProcessIdleTasksCallbackCleanup(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  struct _TP_WAIT *v3; // rcx
  __int64 v4; // rdx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 280);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
  *(_DWORD *)(a1 + 320) |= 2u;
  LeaveCriticalSection(v1);
  v3 = *(struct _TP_WAIT **)(a1 + 352);
  if ( v3 )
  {
    SetThreadpoolWait(v3, 0, 0);
    WaitForThreadpoolWaitCallbacks(*(PTP_WAIT *)(a1 + 352), 1);
    CloseThreadpoolWait(*(PTP_WAIT *)(a1 + 352));
    *(_QWORD *)(a1 + 352) = 0;
  }
  v4 = *(_QWORD *)(a1 + 328);
  if ( v4 )
  {
    PfsIdleTaskMgrUnregister(*(_QWORD *)&PfSvcGlobals + 4104LL, v4, *(_QWORD *)(a1 + 336), *(_QWORD *)(a1 + 344));
    *(_QWORD *)(a1 + 328) = 0;
  }
  EnterCriticalSection(v1);
  *(_DWORD *)(a1 + 320) &= ~2u;
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x180058c88  mov     [rsp+arg_0], rbx
0x180058c8d  push    rdi
0x180058c8e  sub     rsp, 20h
0x180058c92  lea     rdi, [rcx+118h]
0x180058c99  mov     rbx, rcx
0x180058c9c  mov     rcx, rdi; lpCriticalSection
0x180058c9f  call    cs:__imp_EnterCriticalSection
0x180058ca5  or      dword ptr [rbx+140h], 2
0x180058cac  mov     rcx, rdi; lpCriticalSection
0x180058caf  call    cs:__imp_LeaveCriticalSection
0x180058cb5  mov     rcx, [rbx+160h]; pwa
0x180058cbc  test    rcx, rcx
0x180058cbf  jz      short loc_180058CF6
0x180058cc1  xor     r8d, r8d; pftTimeout
0x180058cc4  xor     edx, edx; h
0x180058cc6  call    cs:__imp_SetThreadpoolWait
0x180058ccc  mov     rcx, [rbx+160h]; pwa
0x180058cd3  mov     edx, 1; fCancelPendingCallbacks
0x180058cd8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180058cde  mov     rcx, [rbx+160h]; pwa
0x180058ce5  call    cs:__imp_CloseThreadpoolWait
0x180058ceb  mov     qword ptr [rbx+160h], 0
0x180058cf6  mov     rdx, [rbx+148h]
0x180058cfd  test    rdx, rdx
0x180058d00  jz      short loc_180058D2E
0x180058d02  mov     rcx, cs:PfSvcGlobals
0x180058d09  mov     r9, [rbx+158h]
0x180058d10  add     rcx, 1008h
0x180058d17  mov     r8, [rbx+150h]
0x180058d1e  call    PfsIdleTaskMgrUnregister
0x180058d23  mov     qword ptr [rbx+148h], 0
0x180058d2e  mov     rcx, rdi; lpCriticalSection
0x180058d31  call    cs:__imp_EnterCriticalSection
0x180058d37  and     dword ptr [rbx+140h], 0FFFFFFFDh
0x180058d3e  mov     rcx, rdi
0x180058d41  mov     rbx, [rsp+28h+arg_0]
0x180058d46  add     rsp, 20h
0x180058d4a  pop     rdi
0x180058d4b  jmp     cs:__imp_LeaveCriticalSection
```
