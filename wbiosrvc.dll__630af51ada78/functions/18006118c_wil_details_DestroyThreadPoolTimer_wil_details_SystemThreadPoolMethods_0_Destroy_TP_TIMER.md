# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18006118c`
- end: `0x1800611c0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180058138`
- `0x180058188`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006119d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006119d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800611ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800611ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800611b9`

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
0x18006118c  push    rbx
0x18006118e  sub     rsp, 20h
0x180061192  xor     r9d, r9d; msWindowLength
0x180061195  xor     r8d, r8d; msPeriod
0x180061198  xor     edx, edx; pftDueTime
0x18006119a  mov     rbx, rcx
0x18006119d  call    cs:__imp_SetThreadpoolTimer
0x1800611a3  mov     edx, 1; fCancelPendingCallbacks
0x1800611a8  mov     rcx, rbx; pti
0x1800611ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800611b1  mov     rcx, rbx
0x1800611b4  add     rsp, 20h
0x1800611b8  pop     rbx
0x1800611b9  jmp     cs:__imp_CloseThreadpoolTimer
```
