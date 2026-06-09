# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006e94`
- end: `0x180006ed9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800064c8`
- `0x18000aac0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006ecd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ea5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ea5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006eb9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006eb9`

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
0x180006e94  push    rbx
0x180006e96  sub     rsp, 20h
0x180006e9a  xor     r9d, r9d; msWindowLength
0x180006e9d  xor     r8d, r8d; msPeriod
0x180006ea0  xor     edx, edx; pftDueTime
0x180006ea2  mov     rbx, rcx
0x180006ea5  call    cs:__imp_SetThreadpoolTimer
0x180006eac  nop     dword ptr [rax+rax+00h]
0x180006eb1  mov     edx, 1; fCancelPendingCallbacks
0x180006eb6  mov     rcx, rbx; pti
0x180006eb9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006ec0  nop     dword ptr [rax+rax+00h]
0x180006ec5  mov     rcx, rbx
0x180006ec8  add     rsp, 20h
0x180006ecc  pop     rbx
0x180006ecd  jmp     cs:__imp_CloseThreadpoolTimer
```
