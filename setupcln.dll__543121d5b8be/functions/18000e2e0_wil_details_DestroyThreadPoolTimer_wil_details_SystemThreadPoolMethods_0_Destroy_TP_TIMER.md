# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000e2e0`
- end: `0x18000e314`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d934`
- `0x1800126c4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e2f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e2f1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e2ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e2ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e30d`

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
0x18000e2e0  push    rbx
0x18000e2e2  sub     rsp, 20h
0x18000e2e6  xor     r9d, r9d; msWindowLength
0x18000e2e9  xor     r8d, r8d; msPeriod
0x18000e2ec  xor     edx, edx; pftDueTime
0x18000e2ee  mov     rbx, rcx
0x18000e2f1  call    cs:__imp_SetThreadpoolTimer
0x18000e2f7  mov     edx, 1; fCancelPendingCallbacks
0x18000e2fc  mov     rcx, rbx; pti
0x18000e2ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e305  mov     rcx, rbx
0x18000e308  add     rsp, 20h
0x18000e30c  pop     rbx
0x18000e30d  jmp     cs:__imp_CloseThreadpoolTimer
```
