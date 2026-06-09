# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180037b0c`
- end: `0x180037b40`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002feb8`
- `0x18002ff08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037b2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180037b2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180037b39`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180037b1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180037b1d`

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
0x180037b0c  push    rbx
0x180037b0e  sub     rsp, 20h
0x180037b12  xor     r9d, r9d; msWindowLength
0x180037b15  xor     r8d, r8d; msPeriod
0x180037b18  xor     edx, edx; pftDueTime
0x180037b1a  mov     rbx, rcx
0x180037b1d  call    cs:__imp_SetThreadpoolTimer
0x180037b23  mov     edx, 1; fCancelPendingCallbacks
0x180037b28  mov     rcx, rbx; pti
0x180037b2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180037b31  mov     rcx, rbx
0x180037b34  add     rsp, 20h
0x180037b38  pop     rbx
0x180037b39  jmp     cs:__imp_CloseThreadpoolTimer
```
