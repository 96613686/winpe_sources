# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006d90`
- end: `0x180006dc4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800064a8`
- `0x18000aa40`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006da1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006da1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006dbd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006daf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006daf`

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
0x180006d90  push    rbx
0x180006d92  sub     rsp, 20h
0x180006d96  xor     r9d, r9d; msWindowLength
0x180006d99  xor     r8d, r8d; msPeriod
0x180006d9c  xor     edx, edx; pftDueTime
0x180006d9e  mov     rbx, rcx
0x180006da1  call    cs:__imp_SetThreadpoolTimer
0x180006da7  mov     edx, 1; fCancelPendingCallbacks
0x180006dac  mov     rcx, rbx; pti
0x180006daf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006db5  mov     rcx, rbx
0x180006db8  add     rsp, 20h
0x180006dbc  pop     rbx
0x180006dbd  jmp     cs:__imp_CloseThreadpoolTimer
```
