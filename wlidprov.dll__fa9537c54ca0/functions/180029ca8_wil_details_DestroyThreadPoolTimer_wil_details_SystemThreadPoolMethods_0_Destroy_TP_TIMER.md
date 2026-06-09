# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180029ca8`
- end: `0x180029cdc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001256c`
- `0x180012588`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029cc7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180029cc7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180029cd5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029cb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180029cb9`

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
0x180029ca8  push    rbx
0x180029caa  sub     rsp, 20h
0x180029cae  xor     r9d, r9d; msWindowLength
0x180029cb1  xor     r8d, r8d; msPeriod
0x180029cb4  xor     edx, edx; pftDueTime
0x180029cb6  mov     rbx, rcx
0x180029cb9  call    cs:__imp_SetThreadpoolTimer
0x180029cbf  mov     edx, 1; fCancelPendingCallbacks
0x180029cc4  mov     rcx, rbx; pti
0x180029cc7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180029ccd  mov     rcx, rbx
0x180029cd0  add     rsp, 20h
0x180029cd4  pop     rbx
0x180029cd5  jmp     cs:__imp_CloseThreadpoolTimer
```
