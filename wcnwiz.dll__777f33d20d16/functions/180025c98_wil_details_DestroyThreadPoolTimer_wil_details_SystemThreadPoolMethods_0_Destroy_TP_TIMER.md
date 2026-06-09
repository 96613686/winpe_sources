# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180025c98`
- end: `0x180025ccc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800257c4`
- `0x1800285ac`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180025ca9`
- `KERNEL32!SetThreadpoolTimer` at `0x180025ca9`
- `KERNEL32!CloseThreadpoolTimer` at `0x180025cc5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180025cb7`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180025cb7`

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
0x180025c98  push    rbx
0x180025c9a  sub     rsp, 20h
0x180025c9e  xor     r9d, r9d; msWindowLength
0x180025ca1  xor     r8d, r8d; msPeriod
0x180025ca4  xor     edx, edx; pftDueTime
0x180025ca6  mov     rbx, rcx
0x180025ca9  call    cs:__imp_SetThreadpoolTimer
0x180025caf  mov     edx, 1; fCancelPendingCallbacks
0x180025cb4  mov     rcx, rbx; pti
0x180025cb7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180025cbd  mov     rcx, rbx
0x180025cc0  add     rsp, 20h
0x180025cc4  pop     rbx
0x180025cc5  jmp     cs:__imp_CloseThreadpoolTimer
```
