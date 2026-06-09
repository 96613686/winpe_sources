# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18004c4b4`
- end: `0x18004c4e8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004a3d8`
- `0x1800587c0`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x18004c4e1`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18004c4d3`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18004c4d3`
- `KERNEL32!SetThreadpoolTimer` at `0x18004c4c5`
- `KERNEL32!SetThreadpoolTimer` at `0x18004c4c5`

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
0x18004c4b4  push    rbx
0x18004c4b6  sub     rsp, 20h
0x18004c4ba  xor     r9d, r9d; msWindowLength
0x18004c4bd  xor     r8d, r8d; msPeriod
0x18004c4c0  xor     edx, edx; pftDueTime
0x18004c4c2  mov     rbx, rcx
0x18004c4c5  call    cs:__imp_SetThreadpoolTimer
0x18004c4cb  mov     edx, 1; fCancelPendingCallbacks
0x18004c4d0  mov     rcx, rbx; pti
0x18004c4d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004c4d9  mov     rcx, rbx
0x18004c4dc  add     rsp, 20h
0x18004c4e0  pop     rbx
0x18004c4e1  jmp     cs:__imp_CloseThreadpoolTimer
```
