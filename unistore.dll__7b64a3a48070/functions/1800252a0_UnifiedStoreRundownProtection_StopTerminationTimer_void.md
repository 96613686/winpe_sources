# UnifiedStoreRundownProtection::StopTerminationTimer(void)

- ea: `0x1800252a0`
- end: `0x180025313`
- name: `?StopTerminationTimer@UnifiedStoreRundownProtection@@UEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(UnifiedStoreRundownProtection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002535c`

## callees

- `0x1800252a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800252b6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800252b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800252cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800252cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800252f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800252f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002530b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002530b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025302`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025302`

## pseudocode

```c
__int64 __fastcall UnifiedStoreRundownProtection::StopTerminationTimer(struct _RTL_CRITICAL_SECTION *this)
{
  struct _TP_TIMER *DebugInfo; // rsi

  EnterCriticalSection(this + 2);
  DebugInfo = (struct _TP_TIMER *)this[3].DebugInfo;
  this[3].DebugInfo = 0;
  LeaveCriticalSection(this + 2);
  if ( DebugInfo )
  {
    SetThreadpoolTimer(DebugInfo, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(DebugInfo, 1);
    CloseThreadpoolTimer(DebugInfo);
  }
  return 0;
}

```

## disassembly

```asm
0x1800252a0  mov     [rsp+arg_0], rbx
0x1800252a5  mov     [rsp+arg_8], rsi
0x1800252aa  push    rdi
0x1800252ab  sub     rsp, 20h
0x1800252af  mov     rdi, rcx
0x1800252b2  add     rcx, 50h ; 'P'; lpCriticalSection
0x1800252b6  call    cs:__imp_EnterCriticalSection
0x1800252bc  mov     rsi, [rdi+78h]
0x1800252c0  lea     rcx, [rdi+50h]; lpCriticalSection
0x1800252c4  mov     qword ptr [rdi+78h], 0
0x1800252cc  call    cs:__imp_LeaveCriticalSection
0x1800252d2  test    rsi, rsi
0x1800252d5  jnz     short loc_1800252E9
0x1800252d7  mov     rbx, [rsp+28h+arg_0]
0x1800252dc  xor     eax, eax
0x1800252de  mov     rsi, [rsp+28h+arg_8]
0x1800252e3  add     rsp, 20h
0x1800252e7  pop     rdi
0x1800252e8  retn
0x1800252e9  xor     r9d, r9d; msWindowLength
0x1800252ec  xor     r8d, r8d; msPeriod
0x1800252ef  xor     edx, edx; pftDueTime
0x1800252f1  mov     rcx, rsi; pti
0x1800252f4  call    cs:__imp_SetThreadpoolTimer
0x1800252fa  mov     edx, 1; fCancelPendingCallbacks
0x1800252ff  mov     rcx, rsi; pti
0x180025302  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025308  mov     rcx, rsi; pti
0x18002530b  call    cs:__imp_CloseThreadpoolTimer
0x180025311  jmp     short loc_1800252D7
```
