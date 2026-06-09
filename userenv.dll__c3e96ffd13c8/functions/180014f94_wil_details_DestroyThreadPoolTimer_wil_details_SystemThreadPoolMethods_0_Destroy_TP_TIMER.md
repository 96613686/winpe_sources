# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180014f94`
- end: `0x180014fc8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180014a68`
- `0x180017ca4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014fa5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014fa5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180014fc1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014fb3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014fb3`

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
0x180014f94  push    rbx
0x180014f96  sub     rsp, 20h
0x180014f9a  xor     r9d, r9d; msWindowLength
0x180014f9d  xor     r8d, r8d; msPeriod
0x180014fa0  xor     edx, edx; pftDueTime
0x180014fa2  mov     rbx, rcx
0x180014fa5  call    cs:__imp_SetThreadpoolTimer
0x180014fab  mov     edx, 1; fCancelPendingCallbacks
0x180014fb0  mov     rcx, rbx; pti
0x180014fb3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014fb9  mov     rcx, rbx
0x180014fbc  add     rsp, 20h
0x180014fc0  pop     rbx
0x180014fc1  jmp     cs:__imp_CloseThreadpoolTimer
```
