# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001e2c8`
- end: `0x18001e2fd`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180018660`
- `0x1800186b0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e2e7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e2e7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e2d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e2d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e2f0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e2f0`

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
0x18001e2c8  push    rbx
0x18001e2ca  sub     rsp, 20h
0x18001e2ce  mov     rbx, rcx
0x18001e2d1  xor     r9d, r9d; msWindowLength
0x18001e2d4  xor     r8d, r8d; msPeriod
0x18001e2d7  xor     edx, edx; pftDueTime
0x18001e2d9  call    cs:__imp_SetThreadpoolTimer
0x18001e2df  mov     edx, 1; fCancelPendingCallbacks
0x18001e2e4  mov     rcx, rbx; pti
0x18001e2e7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001e2ed  mov     rcx, rbx; pti
0x18001e2f0  call    cs:__imp_CloseThreadpoolTimer
0x18001e2f6  nop
0x18001e2f7  add     rsp, 20h
0x18001e2fb  pop     rbx
0x18001e2fc  retn
```
