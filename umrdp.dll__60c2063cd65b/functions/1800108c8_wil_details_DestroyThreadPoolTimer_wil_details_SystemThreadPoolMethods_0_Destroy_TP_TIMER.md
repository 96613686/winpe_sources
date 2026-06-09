# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800108c8`
- end: `0x1800108fc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a8cc`
- `0x18000aff0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800108e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800108e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800108f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800108d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800108d9`

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
0x1800108c8  push    rbx
0x1800108ca  sub     rsp, 20h
0x1800108ce  xor     r9d, r9d; msWindowLength
0x1800108d1  xor     r8d, r8d; msPeriod
0x1800108d4  xor     edx, edx; pftDueTime
0x1800108d6  mov     rbx, rcx
0x1800108d9  call    cs:__imp_SetThreadpoolTimer
0x1800108df  mov     edx, 1; fCancelPendingCallbacks
0x1800108e4  mov     rcx, rbx; pti
0x1800108e7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800108ed  mov     rcx, rbx
0x1800108f0  add     rsp, 20h
0x1800108f4  pop     rbx
0x1800108f5  jmp     cs:__imp_CloseThreadpoolTimer
```
