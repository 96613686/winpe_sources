# UL_NATIVE_REQUEST::StartPendingRequestsMonitor(void)

- ea: `0x180013450`
- end: `0x1800134a1`
- name: `?StartPendingRequestsMonitor@UL_NATIVE_REQUEST@@SAJXZ`
- size: `81`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ec08`

## callees

- `0x180013450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013486`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001347c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001347c`

## pseudocode

```c
signed int UL_NATIVE_REQUEST::StartPendingRequestsMonitor(void)
{
  signed int result; // eax

  if ( CreateTimerQueueTimer(
         &UL_NATIVE_REQUEST::sm_hPendingRequestsTimer,
         0,
         UL_NATIVE_REQUEST::PendingRequestsMonitorHandler,
         0,
         0x1388u,
         0x1388u,
         0x10u) )
  {
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180013450  sub     rsp, 48h
0x180013454  mov     eax, 1388h
0x180013459  mov     [rsp+48h+Flags], 10h; Flags
0x180013461  mov     [rsp+48h+Period], eax; Period
0x180013465  lea     r8, ?PendingRequestsMonitorHandler@UL_NATIVE_REQUEST@@SAXPEAXE@Z; Callback
0x18001346c  xor     r9d, r9d; Parameter
0x18001346f  mov     [rsp+48h+DueTime], eax; DueTime
0x180013473  xor     edx, edx; TimerQueue
0x180013475  lea     rcx, ?sm_hPendingRequestsTimer@UL_NATIVE_REQUEST@@0PEAXEA; phNewTimer
0x18001347c  call    cs:__imp_CreateTimerQueueTimer
0x180013482  test    eax, eax
0x180013484  jnz     short loc_18001349A
0x180013486  call    cs:__imp_GetLastError
0x18001348c  test    eax, eax
0x18001348e  jle     short loc_18001349C
0x180013490  movzx   eax, ax
0x180013493  or      eax, 80070000h
0x180013498  jmp     short loc_18001349C
0x18001349a  xor     eax, eax
0x18001349c  add     rsp, 48h
0x1800134a0  retn
```
