# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180005250`
- end: `0x180005284`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004654`
- `0x18000b6e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005261`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005261`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000527d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000526f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000526f`

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
0x180005250  push    rbx
0x180005252  sub     rsp, 20h
0x180005256  xor     r9d, r9d; msWindowLength
0x180005259  xor     r8d, r8d; msPeriod
0x18000525c  xor     edx, edx; pftDueTime
0x18000525e  mov     rbx, rcx
0x180005261  call    cs:__imp_SetThreadpoolTimer
0x180005267  mov     edx, 1; fCancelPendingCallbacks
0x18000526c  mov     rcx, rbx; pti
0x18000526f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005275  mov     rcx, rbx
0x180005278  add     rsp, 20h
0x18000527c  pop     rbx
0x18000527d  jmp     cs:__imp_CloseThreadpoolTimer
```
