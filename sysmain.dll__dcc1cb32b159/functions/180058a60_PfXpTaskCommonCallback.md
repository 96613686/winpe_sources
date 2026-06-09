# PfXpTaskCommonCallback

- ea: `0x180058a60`
- end: `0x180058b22`
- name: `PfXpTaskCommonCallback`
- size: `194`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180058a60`
- `0x180058d58`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058a73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058aaf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058a73`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058aaf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058a8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058a8f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058a83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058a83`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180058a98`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180058a98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058ad1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180058ad1`

## pseudocode

```c
void __fastcall PfXpTaskCommonCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  int v6; // edi

  EnterCriticalSection((LPCRITICAL_SECTION)Context);
  if ( !*((_DWORD *)Context + 13) )
  {
    *((_DWORD *)Context + 13) = GetCurrentThreadId();
    LeaveCriticalSection((LPCRITICAL_SECTION)Context);
    CallbackMayRunLong(Instance);
    v6 = (*((__int64 (__fastcall **)(PVOID))Context + 12))(Context);
    EnterCriticalSection((LPCRITICAL_SECTION)Context);
    if ( *((_DWORD *)Context + 12) == 52943 )
    {
      if ( v6 == 1237 )
      {
        SetThreadpoolWait(*((PTP_WAIT *)Context + 10), *((HANDLE *)Context + 8), 0);
      }
      else
      {
        PfsIdleTaskMgrUnregister(
          *(_QWORD *)&PfSvcGlobals + 4104LL,
          *((_QWORD *)Context + 7),
          *((_QWORD *)Context + 8),
          *((_QWORD *)Context + 9));
        *((_QWORD *)Context + 7) = 0;
        *((_DWORD *)Context + 12) = 52944;
      }
    }
    *((_DWORD *)Context + 13) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)Context);
}

```

## disassembly

```asm
0x180058a60  mov     [rsp+arg_0], rbx
0x180058a65  push    rdi
0x180058a66  sub     rsp, 20h
0x180058a6a  mov     rdi, rcx
0x180058a6d  mov     rbx, rdx
0x180058a70  mov     rcx, rdx; lpCriticalSection
0x180058a73  call    cs:__imp_EnterCriticalSection
0x180058a79  cmp     dword ptr [rbx+34h], 0
0x180058a7d  jnz     loc_180058B0E
0x180058a83  call    cs:__imp_GetCurrentThreadId
0x180058a89  mov     rcx, rbx; lpCriticalSection
0x180058a8c  mov     [rbx+34h], eax
0x180058a8f  call    cs:__imp_LeaveCriticalSection
0x180058a95  mov     rcx, rdi; pci
0x180058a98  call    cs:__imp_CallbackMayRunLong
0x180058a9e  mov     rax, [rbx+60h]
0x180058aa2  mov     rcx, rbx
0x180058aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058aaa  mov     rcx, rbx; lpCriticalSection
0x180058aad  mov     edi, eax
0x180058aaf  call    cs:__imp_EnterCriticalSection
0x180058ab5  cmp     dword ptr [rbx+30h], 0CECFh
0x180058abc  jnz     short loc_180058B07
0x180058abe  cmp     edi, 4D5h
0x180058ac4  jnz     short loc_180058AD9
0x180058ac6  mov     rdx, [rbx+40h]; h
0x180058aca  xor     r8d, r8d; pftTimeout
0x180058acd  mov     rcx, [rbx+50h]; pwa
0x180058ad1  call    cs:__imp_SetThreadpoolWait
0x180058ad7  jmp     short loc_180058B07
0x180058ad9  mov     rcx, cs:PfSvcGlobals
0x180058ae0  mov     r9, [rbx+48h]
0x180058ae4  add     rcx, 1008h
0x180058aeb  mov     r8, [rbx+40h]
0x180058aef  mov     rdx, [rbx+38h]
0x180058af3  call    PfsIdleTaskMgrUnregister
0x180058af8  mov     qword ptr [rbx+38h], 0
0x180058b00  mov     dword ptr [rbx+30h], 0CED0h
0x180058b07  mov     dword ptr [rbx+34h], 0
0x180058b0e  mov     rcx, rbx
0x180058b11  mov     rbx, [rsp+28h+arg_0]
0x180058b16  add     rsp, 20h
0x180058b1a  pop     rdi
0x180058b1b  jmp     cs:__imp_LeaveCriticalSection
```
