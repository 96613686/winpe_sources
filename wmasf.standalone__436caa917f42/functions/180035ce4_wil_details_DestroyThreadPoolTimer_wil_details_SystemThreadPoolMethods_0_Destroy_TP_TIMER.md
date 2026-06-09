# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180035ce4`
- end: `0x180035d18`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800336ac`
- `0x18003c188`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x180035d11`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180035d03`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180035d03`
- `KERNEL32!SetThreadpoolTimer` at `0x180035cf5`
- `KERNEL32!SetThreadpoolTimer` at `0x180035cf5`

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
0x180035ce4  push    rbx
0x180035ce6  sub     rsp, 20h
0x180035cea  xor     r9d, r9d; msWindowLength
0x180035ced  xor     r8d, r8d; msPeriod
0x180035cf0  xor     edx, edx; pftDueTime
0x180035cf2  mov     rbx, rcx
0x180035cf5  call    cs:__imp_SetThreadpoolTimer
0x180035cfb  mov     edx, 1; fCancelPendingCallbacks
0x180035d00  mov     rcx, rbx; pti
0x180035d03  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180035d09  mov     rcx, rbx
0x180035d0c  add     rsp, 20h
0x180035d10  pop     rbx
0x180035d11  jmp     cs:__imp_CloseThreadpoolTimer
```
