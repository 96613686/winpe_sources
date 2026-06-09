# CAudioOrchestratorPolicy::StopCloudSyncWorkerLoop(void)

- ea: `0x1800c4f20`
- end: `0x1800c4fd9`
- name: `?StopCloudSyncWorkerLoop@CAudioOrchestratorPolicy@@UEAAJXZ`
- size: `185`
- prototype: `__int64 __fastcall(CAudioOrchestratorPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800c2f90`

## callees

- `0x180082900`
- `0x18008618c`
- `0x1800c4f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c4f52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800c4f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c4f65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800c4f65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4fb1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c4fb1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c4f99`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800c4f99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c4f8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800c4f8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c4f7a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800c4f7a`

## pseudocode

```c
__int64 __fastcall CAudioOrchestratorPolicy::StopCloudSyncWorkerLoop(CAudioOrchestratorPolicy *this)
{
  void *v2; // rcx
  char v4; // [rsp+30h] [rbp+8h] BYREF

  SpAutoLock::SpAutoLock((SpAutoLock *)&v4, (CAudioOrchestratorPolicy *)((char *)this + 128));
  if ( *((_QWORD *)this + 27) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    *((_DWORD *)this + 52) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
    SetThreadpoolTimer(*((PTP_TIMER *)this + 27), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 27), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 27));
    v2 = (void *)*((_QWORD *)this + 28);
    *((_QWORD *)this + 27) = 0;
    CloseHandle(v2);
    *((_QWORD *)this + 28) = 0;
  }
  SpAutoLock::~SpAutoLock((SpAutoLock *)&v4);
  return 0;
}

```

## disassembly

```asm
0x1800c4f20  mov     [rsp+arg_8], rbx
0x1800c4f25  push    rdi
0x1800c4f26  sub     rsp, 20h
0x1800c4f2a  mov     rdi, rcx
0x1800c4f2d  lea     rdx, [rcx+80h]; struct SpCritSect *
0x1800c4f34  lea     rcx, [rsp+28h+arg_0]; this
0x1800c4f39  call    ??0SpAutoLock@@QEAA@PEAVSpCritSect@@@Z; SpAutoLock::SpAutoLock(SpCritSect *)
0x1800c4f3e  cmp     qword ptr [rdi+0D8h], 0
0x1800c4f46  jz      short loc_1800C4FC2
0x1800c4f48  lea     rbx, [rdi+0A8h]
0x1800c4f4f  mov     rcx, rbx; lpCriticalSection
0x1800c4f52  call    cs:__imp_EnterCriticalSection
0x1800c4f58  mov     rcx, rbx; lpCriticalSection
0x1800c4f5b  mov     dword ptr [rdi+0D0h], 1
0x1800c4f65  call    cs:__imp_LeaveCriticalSection
0x1800c4f6b  mov     rcx, [rdi+0D8h]; pti
0x1800c4f72  xor     r9d, r9d; msWindowLength
0x1800c4f75  xor     r8d, r8d; msPeriod
0x1800c4f78  xor     edx, edx; pftDueTime
0x1800c4f7a  call    cs:__imp_SetThreadpoolTimer
0x1800c4f80  mov     rcx, [rdi+0D8h]; pti
0x1800c4f87  mov     edx, 1; fCancelPendingCallbacks
0x1800c4f8c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800c4f92  mov     rcx, [rdi+0D8h]; pti
0x1800c4f99  call    cs:__imp_CloseThreadpoolTimer
0x1800c4f9f  mov     rcx, [rdi+0E0h]; hObject
0x1800c4fa6  mov     qword ptr [rdi+0D8h], 0
0x1800c4fb1  call    cs:__imp_CloseHandle
0x1800c4fb7  mov     qword ptr [rdi+0E0h], 0
0x1800c4fc2  lea     rcx, [rsp+28h+arg_0]; this
0x1800c4fc7  call    ??1SpAutoLock@@QEAA@XZ; SpAutoLock::~SpAutoLock(void)
0x1800c4fcc  mov     rbx, [rsp+28h+arg_8]
0x1800c4fd1  xor     eax, eax
0x1800c4fd3  add     rsp, 20h
0x1800c4fd7  pop     rdi
0x1800c4fd8  retn
```
