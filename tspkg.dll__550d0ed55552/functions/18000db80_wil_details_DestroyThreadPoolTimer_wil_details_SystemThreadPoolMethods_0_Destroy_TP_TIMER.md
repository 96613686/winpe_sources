# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000db80`
- end: `0x18000dbb4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800097ac`
- `0x18000a268`
- `0x18000a4f4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000db91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000db91`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000dbad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000db9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000db9f`

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
0x18000db80  push    rbx
0x18000db82  sub     rsp, 20h
0x18000db86  xor     r9d, r9d; msWindowLength
0x18000db89  xor     r8d, r8d; msPeriod
0x18000db8c  xor     edx, edx; pftDueTime
0x18000db8e  mov     rbx, rcx
0x18000db91  call    cs:__imp_SetThreadpoolTimer
0x18000db97  mov     edx, 1; fCancelPendingCallbacks
0x18000db9c  mov     rcx, rbx; pti
0x18000db9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000dba5  mov     rcx, rbx
0x18000dba8  add     rsp, 20h
0x18000dbac  pop     rbx
0x18000dbad  jmp     cs:__imp_CloseThreadpoolTimer
```
