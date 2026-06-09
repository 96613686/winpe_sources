# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180066c80`
- end: `0x180066cb4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800347c4`
- `0x180034910`
- `0x1800349c4`
- `0x180069be0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180066cad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180066c9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180066c9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180066c91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180066c91`

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
0x180066c80  push    rbx
0x180066c82  sub     rsp, 20h
0x180066c86  xor     r9d, r9d; msWindowLength
0x180066c89  xor     r8d, r8d; msPeriod
0x180066c8c  xor     edx, edx; pftDueTime
0x180066c8e  mov     rbx, rcx
0x180066c91  call    cs:__imp_SetThreadpoolTimer
0x180066c97  mov     edx, 1; fCancelPendingCallbacks
0x180066c9c  mov     rcx, rbx; pti
0x180066c9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180066ca5  mov     rcx, rbx
0x180066ca8  add     rsp, 20h
0x180066cac  pop     rbx
0x180066cad  jmp     cs:__imp_CloseThreadpoolTimer
```
