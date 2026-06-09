# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002f7d0`
- end: `0x18002f804`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180012f68`
- `0x180016fe4`
- `0x180021294`
- `0x180021360`
- `0x180021420`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f7ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002f7ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002f7fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f7e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002f7e1`

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
0x18002f7d0  push    rbx
0x18002f7d2  sub     rsp, 20h
0x18002f7d6  xor     r9d, r9d; msWindowLength
0x18002f7d9  xor     r8d, r8d; msPeriod
0x18002f7dc  xor     edx, edx; pftDueTime
0x18002f7de  mov     rbx, rcx
0x18002f7e1  call    cs:__imp_SetThreadpoolTimer
0x18002f7e7  mov     edx, 1; fCancelPendingCallbacks
0x18002f7ec  mov     rcx, rbx; pti
0x18002f7ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002f7f5  mov     rcx, rbx
0x18002f7f8  add     rsp, 20h
0x18002f7fc  pop     rbx
0x18002f7fd  jmp     cs:__imp_CloseThreadpoolTimer
```
