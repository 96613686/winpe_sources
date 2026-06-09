# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800362d0`
- end: `0x180036304`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180035824`
- `0x18003a9e8`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800362ef`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800362ef`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800362fd`
- `KERNEL32!SetThreadpoolTimer` at `0x1800362e1`
- `KERNEL32!SetThreadpoolTimer` at `0x1800362e1`

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
0x1800362d0  push    rbx
0x1800362d2  sub     rsp, 20h
0x1800362d6  xor     r9d, r9d; msWindowLength
0x1800362d9  xor     r8d, r8d; msPeriod
0x1800362dc  xor     edx, edx; pftDueTime
0x1800362de  mov     rbx, rcx
0x1800362e1  call    cs:__imp_SetThreadpoolTimer
0x1800362e7  mov     edx, 1; fCancelPendingCallbacks
0x1800362ec  mov     rcx, rbx; pti
0x1800362ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800362f5  mov     rcx, rbx
0x1800362f8  add     rsp, 20h
0x1800362fc  pop     rbx
0x1800362fd  jmp     cs:__imp_CloseThreadpoolTimer
```
