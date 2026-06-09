# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14001355c`
- end: `0x140013590`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14001106c`
- `0x14001da78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140013589`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001356d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001356d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001357b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001357b`

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
0x14001355c  push    rbx
0x14001355e  sub     rsp, 20h
0x140013562  xor     r9d, r9d; msWindowLength
0x140013565  xor     r8d, r8d; msPeriod
0x140013568  xor     edx, edx; pftDueTime
0x14001356a  mov     rbx, rcx
0x14001356d  call    cs:__imp_SetThreadpoolTimer
0x140013573  mov     edx, 1; fCancelPendingCallbacks
0x140013578  mov     rcx, rbx; pti
0x14001357b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140013581  mov     rcx, rbx
0x140013584  add     rsp, 20h
0x140013588  pop     rbx
0x140013589  jmp     cs:__imp_CloseThreadpoolTimer
```
