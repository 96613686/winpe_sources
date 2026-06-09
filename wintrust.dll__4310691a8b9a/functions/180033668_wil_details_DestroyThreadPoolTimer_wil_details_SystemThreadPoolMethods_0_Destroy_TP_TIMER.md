# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180033668`
- end: `0x18003369d`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180022404`
- `0x180022460`
- `0x180025a50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033687`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033687`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033679`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033679`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033690`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033690`

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
0x180033668  push    rbx
0x18003366a  sub     rsp, 20h
0x18003366e  mov     rbx, rcx
0x180033671  xor     r9d, r9d; msWindowLength
0x180033674  xor     r8d, r8d; msPeriod
0x180033677  xor     edx, edx; pftDueTime
0x180033679  call    cs:__imp_SetThreadpoolTimer
0x18003367f  mov     edx, 1; fCancelPendingCallbacks
0x180033684  mov     rcx, rbx; pti
0x180033687  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003368d  mov     rcx, rbx; pti
0x180033690  call    cs:__imp_CloseThreadpoolTimer
0x180033696  nop
0x180033697  add     rsp, 20h
0x18003369b  pop     rbx
0x18003369c  retn
```
