# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000cf50`
- end: `0x18000cf84`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800046d0`
- `0x180004820`
- `0x1800049a0`
- `0x180005590`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cf7d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cf61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cf61`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cf6f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000cf6f`

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
0x18000cf50  push    rbx
0x18000cf52  sub     rsp, 20h
0x18000cf56  xor     r9d, r9d; msWindowLength
0x18000cf59  xor     r8d, r8d; msPeriod
0x18000cf5c  xor     edx, edx; pftDueTime
0x18000cf5e  mov     rbx, rcx
0x18000cf61  call    cs:__imp_SetThreadpoolTimer
0x18000cf67  mov     edx, 1; fCancelPendingCallbacks
0x18000cf6c  mov     rcx, rbx; pti
0x18000cf6f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cf75  mov     rcx, rbx
0x18000cf78  add     rsp, 20h
0x18000cf7c  pop     rbx
0x18000cf7d  jmp     cs:__imp_CloseThreadpoolTimer
```
