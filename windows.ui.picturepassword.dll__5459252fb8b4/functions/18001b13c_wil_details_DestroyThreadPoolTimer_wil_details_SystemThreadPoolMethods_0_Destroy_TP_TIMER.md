# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001b13c`
- end: `0x18001b170`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001acf8`
- `0x18001cd88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b15b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b15b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b169`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b14d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b14d`

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
0x18001b13c  push    rbx
0x18001b13e  sub     rsp, 20h
0x18001b142  xor     r9d, r9d; msWindowLength
0x18001b145  xor     r8d, r8d; msPeriod
0x18001b148  xor     edx, edx; pftDueTime
0x18001b14a  mov     rbx, rcx
0x18001b14d  call    cs:__imp_SetThreadpoolTimer
0x18001b153  mov     edx, 1; fCancelPendingCallbacks
0x18001b158  mov     rcx, rbx; pti
0x18001b15b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b161  mov     rcx, rbx
0x18001b164  add     rsp, 20h
0x18001b168  pop     rbx
0x18001b169  jmp     cs:__imp_CloseThreadpoolTimer
```
