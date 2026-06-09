# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001259c`
- end: `0x1800125d1`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011bd8`
- `0x180014494`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1800125ad`
- `KERNEL32!SetThreadpoolTimer` at `0x1800125ad`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800125c4`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800125c4`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800125bb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800125bb`

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
0x18001259c  push    rbx
0x18001259e  sub     rsp, 20h
0x1800125a2  mov     rbx, rcx
0x1800125a5  xor     r9d, r9d; msWindowLength
0x1800125a8  xor     r8d, r8d; msPeriod
0x1800125ab  xor     edx, edx; pftDueTime
0x1800125ad  call    cs:__imp_SetThreadpoolTimer
0x1800125b3  mov     edx, 1; fCancelPendingCallbacks
0x1800125b8  mov     rcx, rbx; pti
0x1800125bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800125c1  mov     rcx, rbx; pti
0x1800125c4  call    cs:__imp_CloseThreadpoolTimer
0x1800125ca  nop
0x1800125cb  add     rsp, 20h
0x1800125cf  pop     rbx
0x1800125d0  retn
```
