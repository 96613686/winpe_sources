# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001458c`
- end: `0x1800145c1`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180014000`
- `0x180016ae0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001459d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001459d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800145b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800145b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800145ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800145ab`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18001458c  push    rbx
0x18001458e  sub     rsp, 20h
0x180014592  mov     rbx, rcx
0x180014595  xor     r9d, r9d; msWindowLength
0x180014598  xor     r8d, r8d; msPeriod
0x18001459b  xor     edx, edx; pftDueTime
0x18001459d  call    cs:__imp_SetThreadpoolTimer
0x1800145a3  mov     edx, 1; fCancelPendingCallbacks
0x1800145a8  mov     rcx, rbx; pti
0x1800145ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800145b1  mov     rcx, rbx; pti
0x1800145b4  call    cs:__imp_CloseThreadpoolTimer
0x1800145ba  nop
0x1800145bb  add     rsp, 20h
0x1800145bf  pop     rbx
0x1800145c0  retn
```
