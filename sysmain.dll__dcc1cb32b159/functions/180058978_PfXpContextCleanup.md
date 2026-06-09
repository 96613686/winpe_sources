# PfXpContextCleanup

- ea: `0x180058978`
- end: `0x180058a4b`
- name: `PfXpContextCleanup`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x18006a020`

## callees

- `0x180058978`
- `0x180058c88`
- `0x180068f3c`
- `0x18006ed1c`
- `0x18006f594`

## import_xrefs

- `ntdll!NtClose` at `0x180058a04`
- `ntdll!NtClose` at `0x180058a12`
- `ntdll!NtClose` at `0x180058a04`
- `ntdll!NtClose` at `0x180058a12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005898f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005898f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005899f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005899f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058a1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180058a1b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800589d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800589d8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800589b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800589b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800589cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800589cb`

## pseudocode

```c
__int64 __fastcall PfXpContextCleanup(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  struct _TP_TIMER *v3; // rcx
  void *v4; // rcx
  __int64 result; // rax
  __int64 v6; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 280);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
  *(_DWORD *)(a1 + 320) |= 1u;
  LeaveCriticalSection(v1);
  v3 = *(struct _TP_TIMER **)(a1 + 360);
  if ( v3 )
  {
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 360), 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 360));
  }
  PfXpTaskCleanup((LPCRITICAL_SECTION)(a1 + 32));
  PfXpTaskCleanup((LPCRITICAL_SECTION)(a1 + 160));
  PfXpProcessIdleTasksCallbackCleanup(a1);
  v4 = *(void **)(a1 + 8);
  if ( v4 )
    NtClose(v4);
  if ( *(_QWORD *)a1 )
    NtClose(*(HANDLE *)a1);
  DeleteCriticalSection(v1);
  result = PfsMultiStringContextCleanup(a1 + 392);
  if ( (*(_BYTE *)(a1 + 416) & 1) != 0 )
    return PfSvPowerNotifyUnregister(v6, 3);
  return result;
}

```

## disassembly

```asm
0x180058978  mov     [rsp+arg_0], rbx
0x18005897d  push    rdi
0x18005897e  sub     rsp, 20h
0x180058982  lea     rdi, [rcx+118h]
0x180058989  mov     rbx, rcx
0x18005898c  mov     rcx, rdi; lpCriticalSection
0x18005898f  call    cs:__imp_EnterCriticalSection
0x180058995  or      dword ptr [rbx+140h], 1
0x18005899c  mov     rcx, rdi; lpCriticalSection
0x18005899f  call    cs:__imp_LeaveCriticalSection
0x1800589a5  mov     rcx, [rbx+168h]; pti
0x1800589ac  test    rcx, rcx
0x1800589af  jz      short loc_1800589DE
0x1800589b1  xor     r9d, r9d; msWindowLength
0x1800589b4  xor     r8d, r8d; msPeriod
0x1800589b7  xor     edx, edx; pftDueTime
0x1800589b9  call    cs:__imp_SetThreadpoolTimer
0x1800589bf  mov     rcx, [rbx+168h]; pti
0x1800589c6  mov     edx, 1; fCancelPendingCallbacks
0x1800589cb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800589d1  mov     rcx, [rbx+168h]; pti
0x1800589d8  call    cs:__imp_CloseThreadpoolTimer
0x1800589de  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800589e2  call    PfXpTaskCleanup
0x1800589e7  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x1800589ee  call    PfXpTaskCleanup
0x1800589f3  mov     rcx, rbx
0x1800589f6  call    PfXpProcessIdleTasksCallbackCleanup
0x1800589fb  mov     rcx, [rbx+8]; Handle
0x1800589ff  test    rcx, rcx
0x180058a02  jz      short loc_180058A0A
0x180058a04  call    cs:__imp_NtClose
0x180058a0a  mov     rcx, [rbx]; Handle
0x180058a0d  test    rcx, rcx
0x180058a10  jz      short loc_180058A18
0x180058a12  call    cs:__imp_NtClose
0x180058a18  mov     rcx, rdi; lpCriticalSection
0x180058a1b  call    cs:__imp_DeleteCriticalSection
0x180058a21  lea     rcx, [rbx+188h]
0x180058a28  call    PfsMultiStringContextCleanup
0x180058a2d  test    byte ptr [rbx+1A0h], 1
0x180058a34  jz      short loc_180058A40
0x180058a36  mov     edx, 3
0x180058a3b  call    PfSvPowerNotifyUnregister
0x180058a40  mov     rbx, [rsp+28h+arg_0]
0x180058a45  add     rsp, 20h
0x180058a49  pop     rdi
0x180058a4a  retn
```
