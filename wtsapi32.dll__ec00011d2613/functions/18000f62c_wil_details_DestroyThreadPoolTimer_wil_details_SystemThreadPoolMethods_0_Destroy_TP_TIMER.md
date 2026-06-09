# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000f62c`
- end: `0x18000f660`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800064d4`
- `0x1800065cc`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f64b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18000f64b`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000f659`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f63d`
- `KERNEL32!SetThreadpoolTimer` at `0x18000f63d`

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
0x18000f62c  push    rbx
0x18000f62e  sub     rsp, 20h
0x18000f632  xor     r9d, r9d; msWindowLength
0x18000f635  xor     r8d, r8d; msPeriod
0x18000f638  xor     edx, edx; pftDueTime
0x18000f63a  mov     rbx, rcx
0x18000f63d  call    cs:__imp_SetThreadpoolTimer
0x18000f643  mov     edx, 1; fCancelPendingCallbacks
0x18000f648  mov     rcx, rbx; pti
0x18000f64b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f651  mov     rcx, rbx
0x18000f654  add     rsp, 20h
0x18000f658  pop     rbx
0x18000f659  jmp     cs:__imp_CloseThreadpoolTimer
```
