# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002c650`
- end: `0x18002c684`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180027e90`
- `0x18002899c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c66f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c66f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c67d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c661`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c661`

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
0x18002c650  push    rbx
0x18002c652  sub     rsp, 20h
0x18002c656  xor     r9d, r9d; msWindowLength
0x18002c659  xor     r8d, r8d; msPeriod
0x18002c65c  xor     edx, edx; pftDueTime
0x18002c65e  mov     rbx, rcx
0x18002c661  call    cs:__imp_SetThreadpoolTimer
0x18002c667  mov     edx, 1; fCancelPendingCallbacks
0x18002c66c  mov     rcx, rbx; pti
0x18002c66f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002c675  mov     rcx, rbx
0x18002c678  add     rsp, 20h
0x18002c67c  pop     rbx
0x18002c67d  jmp     cs:__imp_CloseThreadpoolTimer
```
