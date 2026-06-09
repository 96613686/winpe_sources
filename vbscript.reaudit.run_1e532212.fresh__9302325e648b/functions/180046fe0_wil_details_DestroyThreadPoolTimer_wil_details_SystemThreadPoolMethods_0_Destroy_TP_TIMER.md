# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180046fe0`
- end: `0x180047014`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18002def0`
- `0x18002f0d8`
- `0x1800416b0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180046ff1`
- `KERNEL32!SetThreadpoolTimer` at `0x180046ff1`
- `KERNEL32!CloseThreadpoolTimer` at `0x18004700d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180046fff`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180046fff`

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
0x180046fe0  push    rbx
0x180046fe2  sub     rsp, 20h
0x180046fe6  xor     r9d, r9d; msWindowLength
0x180046fe9  xor     r8d, r8d; msPeriod
0x180046fec  xor     edx, edx; pftDueTime
0x180046fee  mov     rbx, rcx
0x180046ff1  call    cs:__imp_SetThreadpoolTimer
0x180046ff7  mov     edx, 1; fCancelPendingCallbacks
0x180046ffc  mov     rcx, rbx; pti
0x180046fff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180047005  mov     rcx, rbx
0x180047008  add     rsp, 20h
0x18004700c  pop     rbx
0x18004700d  jmp     cs:__imp_CloseThreadpoolTimer
```
