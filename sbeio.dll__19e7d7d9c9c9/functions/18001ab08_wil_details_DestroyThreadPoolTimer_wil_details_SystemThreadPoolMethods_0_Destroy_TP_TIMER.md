# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001ab08`
- end: `0x18001ab3c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180015820`
- `0x1800272a8`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001ab19`
- `KERNEL32!SetThreadpoolTimer` at `0x18001ab19`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001ab35`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001ab27`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001ab27`

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
0x18001ab08  push    rbx
0x18001ab0a  sub     rsp, 20h
0x18001ab0e  xor     r9d, r9d; msWindowLength
0x18001ab11  xor     r8d, r8d; msPeriod
0x18001ab14  xor     edx, edx; pftDueTime
0x18001ab16  mov     rbx, rcx
0x18001ab19  call    cs:__imp_SetThreadpoolTimer
0x18001ab1f  mov     edx, 1; fCancelPendingCallbacks
0x18001ab24  mov     rcx, rbx; pti
0x18001ab27  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ab2d  mov     rcx, rbx
0x18001ab30  add     rsp, 20h
0x18001ab34  pop     rbx
0x18001ab35  jmp     cs:__imp_CloseThreadpoolTimer
```
