# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002a3c0`
- end: `0x18002a3f4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180020714`
- `0x180020838`
- `0x180020888`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002a3ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a3d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a3d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a3df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a3df`

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
0x18002a3c0  push    rbx
0x18002a3c2  sub     rsp, 20h
0x18002a3c6  xor     r9d, r9d; msWindowLength
0x18002a3c9  xor     r8d, r8d; msPeriod
0x18002a3cc  xor     edx, edx; pftDueTime
0x18002a3ce  mov     rbx, rcx
0x18002a3d1  call    cs:__imp_SetThreadpoolTimer
0x18002a3d7  mov     edx, 1; fCancelPendingCallbacks
0x18002a3dc  mov     rcx, rbx; pti
0x18002a3df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002a3e5  mov     rcx, rbx
0x18002a3e8  add     rsp, 20h
0x18002a3ec  pop     rbx
0x18002a3ed  jmp     cs:__imp_CloseThreadpoolTimer
```
