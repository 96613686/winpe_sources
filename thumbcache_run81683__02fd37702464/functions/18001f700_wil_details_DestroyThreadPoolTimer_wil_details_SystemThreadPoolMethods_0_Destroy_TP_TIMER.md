# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001f700`
- end: `0x18001f734`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001f670`
- `0x180039d4c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f72d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f711`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f711`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f71f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f71f`

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
0x18001f700  push    rbx
0x18001f702  sub     rsp, 20h
0x18001f706  xor     r9d, r9d; msWindowLength
0x18001f709  xor     r8d, r8d; msPeriod
0x18001f70c  xor     edx, edx; pftDueTime
0x18001f70e  mov     rbx, rcx
0x18001f711  call    cs:__imp_SetThreadpoolTimer
0x18001f717  mov     edx, 1; fCancelPendingCallbacks
0x18001f71c  mov     rcx, rbx; pti
0x18001f71f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f725  mov     rcx, rbx
0x18001f728  add     rsp, 20h
0x18001f72c  pop     rbx
0x18001f72d  jmp     cs:__imp_CloseThreadpoolTimer
```
