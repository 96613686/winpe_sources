# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800259e8`
- end: `0x180025a1c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180011b68`
- `0x180023d40`
- `0x1800259a4`
- `0x180027348`
- `0x18003ef2c`
- `0x18004d5b0`
- `0x18004d634`
- `0x180053090`
- `0x1800839c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025a07`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025a07`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025a15`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800259f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800259f9`

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
0x1800259e8  push    rbx
0x1800259ea  sub     rsp, 20h
0x1800259ee  xor     r9d, r9d; msWindowLength
0x1800259f1  xor     r8d, r8d; msPeriod
0x1800259f4  xor     edx, edx; pftDueTime
0x1800259f6  mov     rbx, rcx
0x1800259f9  call    cs:__imp_SetThreadpoolTimer
0x1800259ff  mov     edx, 1; fCancelPendingCallbacks
0x180025a04  mov     rcx, rbx; pti
0x180025a07  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025a0d  mov     rcx, rbx
0x180025a10  add     rsp, 20h
0x180025a14  pop     rbx
0x180025a15  jmp     cs:__imp_CloseThreadpoolTimer
```
