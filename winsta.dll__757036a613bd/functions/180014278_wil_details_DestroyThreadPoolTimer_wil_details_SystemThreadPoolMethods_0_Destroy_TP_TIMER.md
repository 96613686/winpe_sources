# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180014278`
- end: `0x1800142ac`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f750`
- `0x18000f7c4`
- `0x18001097c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800142a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014289`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014289`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014297`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180014297`

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
0x180014278  push    rbx
0x18001427a  sub     rsp, 20h
0x18001427e  xor     r9d, r9d; msWindowLength
0x180014281  xor     r8d, r8d; msPeriod
0x180014284  xor     edx, edx; pftDueTime
0x180014286  mov     rbx, rcx
0x180014289  call    cs:__imp_SetThreadpoolTimer
0x18001428f  mov     edx, 1; fCancelPendingCallbacks
0x180014294  mov     rcx, rbx; pti
0x180014297  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001429d  mov     rcx, rbx
0x1800142a0  add     rsp, 20h
0x1800142a4  pop     rbx
0x1800142a5  jmp     cs:__imp_CloseThreadpoolTimer
```
