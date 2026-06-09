# ProcessorStatisticsBase::Stop(void)

- ea: `0x1402963ec`
- end: `0x140296446`
- name: `?Stop@ProcessorStatisticsBase@@QEAAXXZ`
- size: `90`
- prototype: `void __fastcall(ProcessorStatisticsBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14026d5a0`
- `0x140296358`

## callees

- `0x1402963ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14029642b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14029642b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140296406`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140296406`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14029641b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14029641b`

## pseudocode

```c
void __fastcall ProcessorStatisticsBase::Stop(ProcessorStatisticsBase *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 12), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
}

```

## disassembly

```asm
0x1402963ec  push    rbx
0x1402963ee  sub     rsp, 20h
0x1402963f2  mov     rbx, rcx
0x1402963f5  mov     rcx, [rcx+60h]; pti
0x1402963f9  test    rcx, rcx
0x1402963fc  jz      short loc_14029643F
0x1402963fe  xor     r9d, r9d; msWindowLength
0x140296401  xor     r8d, r8d; msPeriod
0x140296404  xor     edx, edx; pftDueTime
0x140296406  call    cs:__imp_SetThreadpoolTimer
0x14029640d  nop     dword ptr [rax+rax+00h]
0x140296412  mov     rcx, [rbx+60h]; pti
0x140296416  mov     edx, 1; fCancelPendingCallbacks
0x14029641b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140296422  nop     dword ptr [rax+rax+00h]
0x140296427  mov     rcx, [rbx+60h]; pti
0x14029642b  call    cs:__imp_CloseThreadpoolTimer
0x140296432  nop     dword ptr [rax+rax+00h]
0x140296437  mov     qword ptr [rbx+60h], 0
0x14029643f  add     rsp, 20h
0x140296443  pop     rbx
0x140296444  retn
```
