# timeKillEvent

- ea: `0x180003e90`
- end: `0x180003f99`
- name: `timeKillEvent`
- size: `265`
- prototype: `MMRESULT __stdcall(UINT uTimerID)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009120`

## callees

- `0x180003e90`

## import_xrefs

- `ntdll!NtSetEvent` at `0x180003f0d`
- `ntdll!NtSetEvent` at `0x180003f0d`
- `ntdll!NtCancelTimer` at `0x180003ef6`
- `ntdll!NtCancelTimer` at `0x180003ef6`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180003ee1`
- `api-ms-win-mm-time-l1-1-0!timeEndPeriod` at `0x180003ee1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ea8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ea8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f25`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003f91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180003f91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f52`

## pseudocode

```c
MMRESULT __stdcall timeKillEvent(UINT uTimerID)
{
  unsigned __int64 v2; // rbx
  MMRESULT v3; // edi
  BOOL v4; // ebx

  EnterCriticalSection(&TimerThreadCritSec);
  if ( hHandle && (v2 = (unsigned __int64)(uTimerID & 0xF) << 6, *(_DWORD *)((char *)&Events[3] + v2) == uTimerID) )
  {
    timeEndPeriod(*(_DWORD *)((char *)Events + v2 + 4));
    *(_DWORD *)((char *)&Events[3] + v2) = 0;
    v3 = (NtCancelTimer(*(HANDLE *)((char *)&Events[4] + v2), 0) >> 31) & 0x61;
    NtSetEvent(Handle, 0);
    v4 = dword_180026978
      && uTimerID == dword_180026974
      && TimerThreadId != GetCurrentThreadId()
      && (*(_DWORD *)((_BYTE *)&Events[3] + v2 + 4) & 0x100) != 0;
    LeaveCriticalSection(&TimerThreadCritSec);
    if ( !v3 )
    {
      if ( v4 )
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
    }
    return v3;
  }
  else
  {
    LeaveCriticalSection(&TimerThreadCritSec);
    return 97;
  }
}

```

## disassembly

```asm
0x180003e90  mov     [rsp+arg_8], rbx
0x180003e95  mov     [rsp+arg_10], rbp
0x180003e9a  push    rsi
0x180003e9b  sub     rsp, 20h
0x180003e9f  mov     esi, ecx
0x180003ea1  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180003ea8  call    cs:__imp_EnterCriticalSection
0x180003eae  cmp     cs:hHandle, 0
0x180003eb6  jz      loc_180003F71
0x180003ebc  mov     ebx, esi
0x180003ebe  lea     rbp, Events
0x180003ec5  and     ebx, 0Fh
0x180003ec8  shl     rbx, 6
0x180003ecc  mov     eax, [rbx+rbp+18h]
0x180003ed0  cmp     eax, esi
0x180003ed2  jnz     loc_180003F71
0x180003ed8  mov     ecx, [rbx+rbp+4]; uPeriod
0x180003edc  mov     [rsp+28h+arg_0], rdi
0x180003ee1  call    cs:__imp_timeEndPeriod
0x180003ee7  mov     dword ptr [rbx+rbp+18h], 0
0x180003eef  xor     edx, edx; CurrentState
0x180003ef1  mov     rcx, [rbx+rbp+20h]; TimerHandle
0x180003ef6  call    cs:__imp_NtCancelTimer
0x180003efc  mov     rcx, cs:Handle; EventHandle
0x180003f03  xor     edx, edx; PreviousState
0x180003f05  mov     edi, eax
0x180003f07  sar     edi, 1Fh
0x180003f0a  and     edi, 61h
0x180003f0d  call    cs:__imp_NtSetEvent
0x180003f13  cmp     cs:dword_180026978, 0
0x180003f1a  jnz     short loc_180003F4A
0x180003f1c  xor     ebx, ebx
0x180003f1e  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180003f25  call    cs:__imp_LeaveCriticalSection
0x180003f2b  test    edi, edi
0x180003f2d  jnz     short loc_180003F33
0x180003f2f  test    ebx, ebx
0x180003f31  jnz     short loc_180003F85
0x180003f33  mov     eax, edi
0x180003f35  mov     rdi, [rsp+28h+arg_0]
0x180003f3a  mov     rbx, [rsp+28h+arg_8]
0x180003f3f  mov     rbp, [rsp+28h+arg_10]
0x180003f44  add     rsp, 20h
0x180003f48  pop     rsi
0x180003f49  retn
0x180003f4a  cmp     esi, cs:dword_180026974
0x180003f50  jnz     short loc_180003F1C
0x180003f52  call    cs:__imp_GetCurrentThreadId
0x180003f58  cmp     cs:TimerThreadId, eax
0x180003f5e  jz      short loc_180003F1C
0x180003f60  mov     eax, [rbx+rbp+1Ch]
0x180003f64  bt      eax, 8
0x180003f68  jnb     short loc_180003F1C
0x180003f6a  mov     ebx, 1
0x180003f6f  jmp     short loc_180003F1E
0x180003f71  lea     rcx, TimerThreadCritSec; lpCriticalSection
0x180003f78  call    cs:__imp_LeaveCriticalSection
0x180003f7e  mov     eax, 61h ; 'a'
0x180003f83  jmp     short loc_180003F3A
0x180003f85  mov     rcx, cs:hHandle; hHandle
0x180003f8c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x180003f91  call    cs:__imp_WaitForSingleObject
0x180003f97  jmp     short loc_180003F33
```
