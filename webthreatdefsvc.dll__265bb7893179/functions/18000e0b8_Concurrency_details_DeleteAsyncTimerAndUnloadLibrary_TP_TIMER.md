# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x18000e0b8`
- end: `0x18000e0ec`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000d8cc`
- `0x1800110d0`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x18000e0e5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e0d7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000e0d7`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e0c9`
- `KERNEL32!SetThreadpoolTimer` at `0x18000e0c9`

## pseudocode

```c
void __fastcall Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(PTP_TIMER pti, struct _TP_TIMER *a2)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18000e0b8  push    rbx
0x18000e0ba  sub     rsp, 20h
0x18000e0be  xor     r9d, r9d; msWindowLength
0x18000e0c1  xor     r8d, r8d; msPeriod
0x18000e0c4  xor     edx, edx; pftDueTime
0x18000e0c6  mov     rbx, rcx
0x18000e0c9  call    cs:SetThreadpoolTimer
0x18000e0cf  mov     edx, 1; fCancelPendingCallbacks
0x18000e0d4  mov     rcx, rbx; pti
0x18000e0d7  call    cs:WaitForThreadpoolTimerCallbacks
0x18000e0dd  mov     rcx, rbx
0x18000e0e0  add     rsp, 20h
0x18000e0e4  pop     rbx
0x18000e0e5  jmp     cs:CloseThreadpoolTimer
```
