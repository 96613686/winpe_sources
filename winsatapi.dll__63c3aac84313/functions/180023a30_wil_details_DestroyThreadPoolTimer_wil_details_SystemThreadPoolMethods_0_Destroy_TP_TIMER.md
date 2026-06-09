# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180023a30`
- end: `0x180023a64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f3b0`
- `0x18000f490`
- `0x1800112fc`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180023a41`
- `KERNEL32!SetThreadpoolTimer` at `0x180023a41`
- `KERNEL32!CloseThreadpoolTimer` at `0x180023a5d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180023a4f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180023a4f`

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
0x180023a30  push    rbx
0x180023a32  sub     rsp, 20h
0x180023a36  xor     r9d, r9d; msWindowLength
0x180023a39  xor     r8d, r8d; msPeriod
0x180023a3c  xor     edx, edx; pftDueTime
0x180023a3e  mov     rbx, rcx
0x180023a41  call    cs:__imp_SetThreadpoolTimer
0x180023a47  mov     edx, 1; fCancelPendingCallbacks
0x180023a4c  mov     rcx, rbx; pti
0x180023a4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023a55  mov     rcx, rbx
0x180023a58  add     rsp, 20h
0x180023a5c  pop     rbx
0x180023a5d  jmp     cs:__imp_CloseThreadpoolTimer
```
