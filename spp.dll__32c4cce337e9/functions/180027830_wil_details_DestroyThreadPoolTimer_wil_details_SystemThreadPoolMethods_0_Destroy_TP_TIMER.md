# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180027830`
- end: `0x180027864`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800273a8`
- `0x18002b3b0`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180027841`
- `KERNEL32!SetThreadpoolTimer` at `0x180027841`
- `KERNEL32!CloseThreadpoolTimer` at `0x18002785d`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002784f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18002784f`

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
0x180027830  push    rbx
0x180027832  sub     rsp, 20h
0x180027836  xor     r9d, r9d; msWindowLength
0x180027839  xor     r8d, r8d; msPeriod
0x18002783c  xor     edx, edx; pftDueTime
0x18002783e  mov     rbx, rcx
0x180027841  call    cs:__imp_SetThreadpoolTimer
0x180027847  mov     edx, 1; fCancelPendingCallbacks
0x18002784c  mov     rcx, rbx; pti
0x18002784f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180027855  mov     rcx, rbx
0x180027858  add     rsp, 20h
0x18002785c  pop     rbx
0x18002785d  jmp     cs:__imp_CloseThreadpoolTimer
```
